# LDN Talks January 2020

## Chris Whealy on Pororus_Absorber

- Speaker - [Chris Whealy](http://whealy.com/) https://twitter.com/LogaRhythm
  - He is a drummer and home practice is what motivated him to build an acoustic environment
- Project - [Pororus_Absorber](https://github.com/ChrisWhealy/porous_absorber)
  - App is designed to assist acousticians when designing environments such as home cinemas 
  - It calculates the acoustic absorption curve of a variety of absorption devices mounted against a rigid backing such as a brick wall
  - This is a Rust-WASM project which is a port of an Excel sheet he wrote about 15 years ago using VBScript!
- This was his first Rust WASM project and due to that it took about three months for this project.
- Maths for acoustic calculations were not new to him and they were basically ports from Excel to Rust.
- If done again, he mentioned that he would be able to do the project in a couple of weeks now.
- Some design decisions, such as using JavaScript for event handling could be revisited if reimplemented from scratch.
  - Since WASM allows capturing the DOM at the start, even handling _can_ be done completely within Rust-WASM.
  - For some functions he is passing simply `JSObjects`, which can stand for _anything_ - this is something he found that he preferred from experience given that obscure error messages one gets if type conversions fail w.r.t. more specific parameters.
  
## Andrius Aucinas on Brave adblock improvements with Rust

- [Andrius Aucinas](https://uk.linkedin.com/in/andriusaucinas) is a performance researcher at Brave and was previously the Head of Engineering at HAT (Hub of All Things), which he co-founded.
- Andrius' Twitter - https://twitter.com/AndriusAuc
- Project - https://github.com/brave/adblock-rust
- He is part of the team responsible for porting Brave Browser's AdBlock engine over from C++ to Rust, he'll be sharing some insights and experiences of that development process.
- Pointers from the talk
  - Used Apple Instruments for profiling
  - Algorithmic improvements were far more important than the optimisation potential of Rust vs C++
  - Blocking alogorithm is now close to uBlock's implementation
  - Brave does uBlock like filtering but also some fingerprinting protectoin which uBlock cannot do since it is not as integrated to the core
  - Brave and other vendors fund the Easylist maintainer which is an open source collaborative effort
  - Thanks to really optimised libraries (which does use `unsafe` for performance reasons) this new code did *not* have to use `unsafe`
    - Rust unsafe code can be disabled by setting following macro - <https://doc.rust-lang.org/nomicon/safe-unsafe-meaning.html>,
      ```rust
      #![forbid(unsafe_code)]
      ```
  - One of the surprising speedups was using ASCII for string processing, instead of UTF when it was possible to. This is something I have also observed even in Java code. It is a known optimisation in [InternetDomainName](https://guava.dev/releases/24.0-jre/api/docs/com/google/common/net/InternetDomainName.html), for example, to use Ascii internally, when possible.
  - Even though not used by this specific code, SMID optimisations used by the libraries make a huge difference.
