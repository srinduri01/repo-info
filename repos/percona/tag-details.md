<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `percona`

-	[`percona:5.7.17`](#percona5717)
-	[`percona:5.7`](#percona57)
-	[`percona:5`](#percona5)
-	[`percona:latest`](#perconalatest)
-	[`percona:5.6.35`](#percona5635)
-	[`percona:5.6`](#percona56)
-	[`percona:5.5.54`](#percona5554)
-	[`percona:5.5`](#percona55)

## `percona:5.7.17`

```console
$ docker pull percona@sha256:75d4dd1f9f6851372f0a400843a657722240f964822120b036c0740d64c350fe
```

-	Platforms:
	-	linux; amd64

### `percona:5.7.17` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **125.7 MB (125709420 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:283ef2185b79f8396b897a72ca2bee620180bb483f760819242a4b5f1f12556f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:53:18 GMT
ENV PERCONA_MAJOR=5.7
# Thu, 30 Mar 2017 22:02:14 GMT
ENV PERCONA_VERSION=5.7.17-12-1.jessie
# Thu, 30 Mar 2017 22:02:37 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 30 Mar 2017 22:02:38 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 30 Mar 2017 22:02:39 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 30 Mar 2017 22:02:40 GMT
COPY file:01e6982f4616ce5335aa8fc1b158e02657d5596a595c569bb9febb58755d8095 in /usr/local/bin/ 
# Thu, 30 Mar 2017 22:02:41 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 30 Mar 2017 22:02:42 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Mar 2017 22:02:43 GMT
EXPOSE 3306/tcp
# Thu, 30 Mar 2017 22:02:44 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6dbc1f1f20fa4332a2cee8a7809911dad8d14a752016d8a0b1b1e8ad69d24954`  
		Last Modified: Thu, 30 Mar 2017 22:04:00 GMT  
		Size: 66.4 MB (66432054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1acecc0ba1fb744bc71b064e3a68a76b0a622995afb3ef21869a0a2d38d25adc`  
		Last Modified: Thu, 30 Mar 2017 22:03:40 GMT  
		Size: 708.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5519099d84a165565a9da46fd9d24a56999bcc30c21b44930a218a2fc416a6e5`  
		Last Modified: Thu, 30 Mar 2017 22:03:42 GMT  
		Size: 2.1 KB (2132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0feb9bcec3a8da31a66dbdba6f6f1b5577896b0f4a75a54174f1b162d715e243`  
		Last Modified: Thu, 30 Mar 2017 22:03:41 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.7`

```console
$ docker pull percona@sha256:75d4dd1f9f6851372f0a400843a657722240f964822120b036c0740d64c350fe
```

-	Platforms:
	-	linux; amd64

### `percona:5.7` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **125.7 MB (125709420 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:283ef2185b79f8396b897a72ca2bee620180bb483f760819242a4b5f1f12556f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:53:18 GMT
ENV PERCONA_MAJOR=5.7
# Thu, 30 Mar 2017 22:02:14 GMT
ENV PERCONA_VERSION=5.7.17-12-1.jessie
# Thu, 30 Mar 2017 22:02:37 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 30 Mar 2017 22:02:38 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 30 Mar 2017 22:02:39 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 30 Mar 2017 22:02:40 GMT
COPY file:01e6982f4616ce5335aa8fc1b158e02657d5596a595c569bb9febb58755d8095 in /usr/local/bin/ 
# Thu, 30 Mar 2017 22:02:41 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 30 Mar 2017 22:02:42 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Mar 2017 22:02:43 GMT
EXPOSE 3306/tcp
# Thu, 30 Mar 2017 22:02:44 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6dbc1f1f20fa4332a2cee8a7809911dad8d14a752016d8a0b1b1e8ad69d24954`  
		Last Modified: Thu, 30 Mar 2017 22:04:00 GMT  
		Size: 66.4 MB (66432054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1acecc0ba1fb744bc71b064e3a68a76b0a622995afb3ef21869a0a2d38d25adc`  
		Last Modified: Thu, 30 Mar 2017 22:03:40 GMT  
		Size: 708.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5519099d84a165565a9da46fd9d24a56999bcc30c21b44930a218a2fc416a6e5`  
		Last Modified: Thu, 30 Mar 2017 22:03:42 GMT  
		Size: 2.1 KB (2132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0feb9bcec3a8da31a66dbdba6f6f1b5577896b0f4a75a54174f1b162d715e243`  
		Last Modified: Thu, 30 Mar 2017 22:03:41 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5`

```console
$ docker pull percona@sha256:75d4dd1f9f6851372f0a400843a657722240f964822120b036c0740d64c350fe
```

-	Platforms:
	-	linux; amd64

### `percona:5` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **125.7 MB (125709420 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:283ef2185b79f8396b897a72ca2bee620180bb483f760819242a4b5f1f12556f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:53:18 GMT
ENV PERCONA_MAJOR=5.7
# Thu, 30 Mar 2017 22:02:14 GMT
ENV PERCONA_VERSION=5.7.17-12-1.jessie
# Thu, 30 Mar 2017 22:02:37 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 30 Mar 2017 22:02:38 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 30 Mar 2017 22:02:39 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 30 Mar 2017 22:02:40 GMT
COPY file:01e6982f4616ce5335aa8fc1b158e02657d5596a595c569bb9febb58755d8095 in /usr/local/bin/ 
# Thu, 30 Mar 2017 22:02:41 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 30 Mar 2017 22:02:42 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Mar 2017 22:02:43 GMT
EXPOSE 3306/tcp
# Thu, 30 Mar 2017 22:02:44 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6dbc1f1f20fa4332a2cee8a7809911dad8d14a752016d8a0b1b1e8ad69d24954`  
		Last Modified: Thu, 30 Mar 2017 22:04:00 GMT  
		Size: 66.4 MB (66432054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1acecc0ba1fb744bc71b064e3a68a76b0a622995afb3ef21869a0a2d38d25adc`  
		Last Modified: Thu, 30 Mar 2017 22:03:40 GMT  
		Size: 708.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5519099d84a165565a9da46fd9d24a56999bcc30c21b44930a218a2fc416a6e5`  
		Last Modified: Thu, 30 Mar 2017 22:03:42 GMT  
		Size: 2.1 KB (2132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0feb9bcec3a8da31a66dbdba6f6f1b5577896b0f4a75a54174f1b162d715e243`  
		Last Modified: Thu, 30 Mar 2017 22:03:41 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:latest`

```console
$ docker pull percona@sha256:75d4dd1f9f6851372f0a400843a657722240f964822120b036c0740d64c350fe
```

-	Platforms:
	-	linux; amd64

### `percona:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **125.7 MB (125709420 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:283ef2185b79f8396b897a72ca2bee620180bb483f760819242a4b5f1f12556f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:53:18 GMT
ENV PERCONA_MAJOR=5.7
# Thu, 30 Mar 2017 22:02:14 GMT
ENV PERCONA_VERSION=5.7.17-12-1.jessie
# Thu, 30 Mar 2017 22:02:37 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 30 Mar 2017 22:02:38 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 30 Mar 2017 22:02:39 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 30 Mar 2017 22:02:40 GMT
COPY file:01e6982f4616ce5335aa8fc1b158e02657d5596a595c569bb9febb58755d8095 in /usr/local/bin/ 
# Thu, 30 Mar 2017 22:02:41 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 30 Mar 2017 22:02:42 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Mar 2017 22:02:43 GMT
EXPOSE 3306/tcp
# Thu, 30 Mar 2017 22:02:44 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6dbc1f1f20fa4332a2cee8a7809911dad8d14a752016d8a0b1b1e8ad69d24954`  
		Last Modified: Thu, 30 Mar 2017 22:04:00 GMT  
		Size: 66.4 MB (66432054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1acecc0ba1fb744bc71b064e3a68a76b0a622995afb3ef21869a0a2d38d25adc`  
		Last Modified: Thu, 30 Mar 2017 22:03:40 GMT  
		Size: 708.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5519099d84a165565a9da46fd9d24a56999bcc30c21b44930a218a2fc416a6e5`  
		Last Modified: Thu, 30 Mar 2017 22:03:42 GMT  
		Size: 2.1 KB (2132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0feb9bcec3a8da31a66dbdba6f6f1b5577896b0f4a75a54174f1b162d715e243`  
		Last Modified: Thu, 30 Mar 2017 22:03:41 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.6.35`

```console
$ docker pull percona@sha256:d3c9efa01972b397a15314c2eac473891e071879ecee1cf6b940930161ae5d73
```

-	Platforms:
	-	linux; amd64

### `percona:5.6.35` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **111.3 MB (111290322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:98ffb573d65e9100ce354a2b1511c6602a5ed7105e3e8a81e2d32446e3528c96`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:55:02 GMT
ENV PERCONA_MAJOR=5.6
# Thu, 30 Mar 2017 22:02:45 GMT
ENV PERCONA_VERSION=5.6.35-81.0-1.jessie
# Thu, 30 Mar 2017 22:03:12 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 30 Mar 2017 22:03:14 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 30 Mar 2017 22:03:14 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 30 Mar 2017 22:03:15 GMT
COPY file:4bddc4758e22941cff70200b3c2b9944da22d0dd3b359657e1d240679abc379b in /usr/local/bin/ 
# Thu, 30 Mar 2017 22:03:17 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 30 Mar 2017 22:03:18 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Mar 2017 22:03:18 GMT
EXPOSE 3306/tcp
# Thu, 30 Mar 2017 22:03:19 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37afbbe801c9ae21d2c0f78a69ea2e19a30db86777c2a868212e3029cf7488b5`  
		Last Modified: Thu, 30 Mar 2017 22:05:39 GMT  
		Size: 52.0 MB (52011775 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb34d76ec704d6151bb06e19edbc0bcf780246623ec14012a0b0e995594990ff`  
		Last Modified: Thu, 30 Mar 2017 22:05:24 GMT  
		Size: 1.9 KB (1888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d95f8d05004dbb2e28470614a7f0e0c80033968a147aba87206b8ca41c5d0b68`  
		Last Modified: Thu, 30 Mar 2017 22:05:24 GMT  
		Size: 2.1 KB (2133 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8c19c03c458a05fbd5d4d61b079606bef912131ea195264a2febc1bd4cc60e0`  
		Last Modified: Thu, 30 Mar 2017 22:05:24 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.6`

```console
$ docker pull percona@sha256:d3c9efa01972b397a15314c2eac473891e071879ecee1cf6b940930161ae5d73
```

-	Platforms:
	-	linux; amd64

### `percona:5.6` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **111.3 MB (111290322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:98ffb573d65e9100ce354a2b1511c6602a5ed7105e3e8a81e2d32446e3528c96`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:55:02 GMT
ENV PERCONA_MAJOR=5.6
# Thu, 30 Mar 2017 22:02:45 GMT
ENV PERCONA_VERSION=5.6.35-81.0-1.jessie
# Thu, 30 Mar 2017 22:03:12 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 30 Mar 2017 22:03:14 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 30 Mar 2017 22:03:14 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 30 Mar 2017 22:03:15 GMT
COPY file:4bddc4758e22941cff70200b3c2b9944da22d0dd3b359657e1d240679abc379b in /usr/local/bin/ 
# Thu, 30 Mar 2017 22:03:17 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 30 Mar 2017 22:03:18 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Mar 2017 22:03:18 GMT
EXPOSE 3306/tcp
# Thu, 30 Mar 2017 22:03:19 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37afbbe801c9ae21d2c0f78a69ea2e19a30db86777c2a868212e3029cf7488b5`  
		Last Modified: Thu, 30 Mar 2017 22:05:39 GMT  
		Size: 52.0 MB (52011775 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb34d76ec704d6151bb06e19edbc0bcf780246623ec14012a0b0e995594990ff`  
		Last Modified: Thu, 30 Mar 2017 22:05:24 GMT  
		Size: 1.9 KB (1888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d95f8d05004dbb2e28470614a7f0e0c80033968a147aba87206b8ca41c5d0b68`  
		Last Modified: Thu, 30 Mar 2017 22:05:24 GMT  
		Size: 2.1 KB (2133 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8c19c03c458a05fbd5d4d61b079606bef912131ea195264a2febc1bd4cc60e0`  
		Last Modified: Thu, 30 Mar 2017 22:05:24 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.5.54`

```console
$ docker pull percona@sha256:10bc6316d5ed59705d4507ec87ba155c43aa6d65343ef7c45975a7a1ae88cd9e
```

-	Platforms:
	-	linux; amd64

### `percona:5.5.54` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.8 MB (103787938 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7cfeb2290d5f7b82f19f04a26881154ff93937ede8ef6c97a015ed4a6909f495`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:53:52 GMT
ENV PERCONA_MAJOR=5.5
# Thu, 23 Mar 2017 00:01:36 GMT
ENV PERCONA_VERSION=5.5.54-rel38.7-1.jessie
# Thu, 23 Mar 2017 00:02:33 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 23 Mar 2017 00:02:35 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 23 Mar 2017 00:02:36 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 23 Mar 2017 00:02:38 GMT
COPY file:4bddc4758e22941cff70200b3c2b9944da22d0dd3b359657e1d240679abc379b in /usr/local/bin/ 
# Thu, 23 Mar 2017 00:02:40 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 23 Mar 2017 00:02:41 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 23 Mar 2017 00:02:42 GMT
EXPOSE 3306/tcp
# Thu, 23 Mar 2017 00:02:43 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6feb689553c3ef1f271921df3900c49b23a2c684dbea10f51233ed21970e726d`  
		Last Modified: Thu, 23 Mar 2017 00:07:32 GMT  
		Size: 44.5 MB (44509393 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:342ac1be0bd8fea888e5857696f432aac8eaa485b1459c7d38da0f4884659d68`  
		Last Modified: Thu, 23 Mar 2017 00:07:09 GMT  
		Size: 1.9 KB (1888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ac231c219a900b002b692d8339df731401d23685a5d41aef6ffc03dc113997f`  
		Last Modified: Thu, 23 Mar 2017 00:07:09 GMT  
		Size: 2.1 KB (2132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a426c8bf433b5cb7e7f8f2d8f21dd57bad4466202b64cb4e3068ff7f8a80c0c`  
		Last Modified: Thu, 23 Mar 2017 00:07:09 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.5`

```console
$ docker pull percona@sha256:10bc6316d5ed59705d4507ec87ba155c43aa6d65343ef7c45975a7a1ae88cd9e
```

-	Platforms:
	-	linux; amd64

### `percona:5.5` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.8 MB (103787938 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7cfeb2290d5f7b82f19f04a26881154ff93937ede8ef6c97a015ed4a6909f495`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:57:08 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 21 Mar 2017 20:57:08 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 20:57:23 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 20:57:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 21 Mar 2017 20:57:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:53:13 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 21 Mar 2017 22:53:16 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 21 Mar 2017 22:53:17 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 21 Mar 2017 22:53:52 GMT
ENV PERCONA_MAJOR=5.5
# Thu, 23 Mar 2017 00:01:36 GMT
ENV PERCONA_VERSION=5.5.54-rel38.7-1.jessie
# Thu, 23 Mar 2017 00:02:33 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Thu, 23 Mar 2017 00:02:35 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Thu, 23 Mar 2017 00:02:36 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Thu, 23 Mar 2017 00:02:38 GMT
COPY file:4bddc4758e22941cff70200b3c2b9944da22d0dd3b359657e1d240679abc379b in /usr/local/bin/ 
# Thu, 23 Mar 2017 00:02:40 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 23 Mar 2017 00:02:41 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 23 Mar 2017 00:02:42 GMT
EXPOSE 3306/tcp
# Thu, 23 Mar 2017 00:02:43 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0929eb7dfe716f6e8edb212623ecc441984079645217bc2fb9ed9c04924380`  
		Last Modified: Thu, 23 Mar 2017 00:03:18 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03f348dc3b9d8c4af8e0fa572d4eb7ef0c5e238d87e9d09513662159d32b4634`  
		Last Modified: Thu, 23 Mar 2017 00:03:17 GMT  
		Size: 1.3 MB (1288974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd337761ca76fcbda6892c860c2a01288d50e66b7641500139dac7159fdc5a6c`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f124cc3249602444e72a2377ed7fb3ecb6584b00864d2adbf452620f9a3c896a`  
		Last Modified: Thu, 23 Mar 2017 00:03:19 GMT  
		Size: 6.5 MB (6539918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2cc0ee3b25a94a5eb351eccc05f32d38c47e3f286428f7f8c3ae573d1fbb80`  
		Last Modified: Thu, 23 Mar 2017 00:03:16 GMT  
		Size: 4.7 KB (4667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fdad716af51919a46dc6f7b94fe2214b82b028295696cd8ddd8e74f0c339178`  
		Last Modified: Thu, 23 Mar 2017 00:03:13 GMT  
		Size: 210.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6feb689553c3ef1f271921df3900c49b23a2c684dbea10f51233ed21970e726d`  
		Last Modified: Thu, 23 Mar 2017 00:07:32 GMT  
		Size: 44.5 MB (44509393 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:342ac1be0bd8fea888e5857696f432aac8eaa485b1459c7d38da0f4884659d68`  
		Last Modified: Thu, 23 Mar 2017 00:07:09 GMT  
		Size: 1.9 KB (1888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ac231c219a900b002b692d8339df731401d23685a5d41aef6ffc03dc113997f`  
		Last Modified: Thu, 23 Mar 2017 00:07:09 GMT  
		Size: 2.1 KB (2132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a426c8bf433b5cb7e7f8f2d8f21dd57bad4466202b64cb4e3068ff7f8a80c0c`  
		Last Modified: Thu, 23 Mar 2017 00:07:09 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
