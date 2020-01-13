# Docker

## Background

- Docker on macOS uses [HyperKit](https://github.com/moby/hyperkit) - <http://collabnix.com/how-docker-for-mac-works-under-the-hood/>

## Usage

- To delete all containers including its volumes use,

  `docker rm -vf $(docker ps -a -q)`

- To delete all the images,

  `docker rmi -f $(docker images -a -q)`

- Connect to Postgres docker container with `psql` (in `fish` shell syntax),

  `docker exec -it (docker ps | grep postgres | cut -f1 -d' ') psql -U sa postgres`

  This is a useful technique which can be generalised to work in other contexts.
