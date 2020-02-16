# Scalable Component Abstractions

- Read Date - 2020-02-16

- Fixed `SubjectObserver` example,

```scala
abstract class SubjectObserver {
  type S <: Subject
  type O <: Observer

  abstract class Subject {
    self : S =>

    private var observers: List[O] = List()

    def subscribe(obs: O): Unit = observers = obs :: observers

    def publish(): Unit =
      for (obs <- observers) obs.notify(self)
  }

  abstract class Observer {
    def notify(sub: S): Unit
  }
}

object SensorReader extends SubjectObserver {
  type S = Sensor
  type O = Display

  abstract class Sensor extends Subject {
    val label: String
    var value: Double = 0.0

    def changeValue(v: Double): Unit = {
      value = v
      publish()
    }
  }

  class Display extends Observer {
    override def notify(sub: Sensor): Unit =
      println(s"${sub.label} has value ${sub.value}")
  }

}
```

