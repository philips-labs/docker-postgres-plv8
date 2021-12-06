# postgres-plv8

Docker images for running [plv8](https://github.com/plv8/plv8) 2.3.15 on Postgres 10, 11 and 12. Based on the [official Postgres image](http://registry.hub.docker.com/_/postgres/).

[![philipslabs/postgres-plv8][docker-pulls-image]][docker-hub-url] [![philipslabs/postgres-plv8][docker-stars-image]][docker-hub-url] [![philipslabs/postgres-plv8][docker-size-image]][docker-hub-url] [![philipslabs/postgres-plv8][docker-layers-image]][docker-hub-url]

## Tags

- `12`, `latest` ([12/Dockerfile](https://github.com/philips-labs/docker-postgres-plv8/blob/master/12/Dockerfile))
- `11` ([11-2/Dockerfile](https://github.com/philips-labs/docker-postgres-plv8/blob/master/11/Dockerfile))
- `10` ([10-2/Dockerfile](https://github.com/philips-labs/docker-postgres-plv8/blob/master/10/Dockerfile))

## Usage

### How to use this image

This image behaves exactly like the official Postgres image with the only difference being the inclusion of the plv8 extension.

```sh
$ docker run -d --name postgres philipslabs/postgres-plv8
$ docker exec -it postgres bash -c "psql -U postgres -c \"CREATE EXTENSION plv8; SELECT extversion FROM pg_extension WHERE extname = 'plv8';\""
```

You should see the version of the plv8 extension installed.

You can optionally create a service using `docker-compose`:

```yml
postgres:
  image: philipslabs/postgres-plv8
```

## Image variants

The `philipslabs/postgres-plv8` image comes in multiple flavors:

### `philipslabs/postgres-plv8:latest`

Points to the latest release available of Postgres stable with compatible plv8 installed. Occasionally pre-release versions will be included.

### `philipslabs/postgres-plv8:<majorPostgresVersion>`

Points to the latest release available of Postgres `<majorPostgresVersion>` with the latest release available of plv8 installed.

## Supported Docker versions

This image is officially supported on Docker version 19.03, with support for older versions provided on a best-effort basis.

## License

MIT

[docker-hub-url]: https://hub.docker.com/r/philipslabs/postgres-plv8/
[docker-pulls-image]: https://img.shields.io/docker/pulls/philipslabs/postgres-plv8.svg?style=flat-square
[docker-stars-image]: https://img.shields.io/docker/stars/philipslabs/postgres-plv8.svg?style=flat-square
[docker-layers-image]: https://img.shields.io/microbadger/layers/philipslabs/postgres-plv8.svg?style=flat-square
[docker-size-image]: https://img.shields.io/microbadger/image-size/philipslabs/postgres-plv8.svg?style=flat-square
