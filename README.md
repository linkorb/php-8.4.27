# php-8.4.27

Temporary stand-in for the Docker Official Image `php:8.4.27-apache-bookworm`.

PHP 8.4.27 is on php.net. [docker-library/php#1694](https://github.com/docker-library/php/pull/1694) merged the version bump at `e3eaff845f7a9f7259c31da54dce0320b47a3bbd`. Publishing still waits on [docker-library/official-images#22541](https://github.com/docker-library/official-images/pull/22541) and the official image build. This repo builds that one variant from the upstream Dockerfile, unchanged.

```dockerfile
FROM ghcr.io/linkorb/php-8.4.27:8.4.27-apache-bookworm
```

That replaces `FROM php:8.4.27-apache-bookworm`. Drop the pin when the official tag exists.

The image is `linux/amd64` only. The Dockerfile and the `docker-php-*` and `apache2-foreground` scripts are the `8.4/bookworm/apache` tree at the commit in `SOURCE.yaml`. `LICENSE` is the upstream MIT license.

```sh
docker build -t php:8.4.27-apache-bookworm .
```

A push to `main` builds the same Dockerfile and pushes `ghcr.io/linkorb/php-8.4.27:8.4.27-apache-bookworm`.
