<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `consul`

-	[`consul:latest`](#consullatest)
-	[`consul:0.7.5`](#consul075)

## `consul:latest`

```console
$ docker pull consul@sha256:7fa3365242fca70d63e8e9737f4f1ac8687987d04bbdb7287bc80ea813e624ca
```

-	Platforms:
	-	linux; amd64

### `consul:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **12.9 MB (12907123 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b3dc6a88e25172c0006e6ef5512078fbc23c09d97cf4f10ab535821c83c46953`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["agent","-dev","-client","0.0.0.0"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 21:46:33 GMT
MAINTAINER James Phillips <james@hashicorp.com> (@slackpad)
# Fri, 03 Mar 2017 21:46:33 GMT
ENV CONSUL_VERSION=0.7.5
# Fri, 03 Mar 2017 21:46:33 GMT
ENV DOCKER_BASE_VERSION=0.0.4
# Fri, 03 Mar 2017 21:46:34 GMT
ENV HASHICORP_RELEASES=https://releases.hashicorp.com
# Fri, 03 Mar 2017 21:46:34 GMT
RUN addgroup consul &&     adduser -S -G consul consul
# Fri, 03 Mar 2017 21:46:43 GMT
RUN apk add --no-cache ca-certificates curl gnupg libcap openssl &&     gpg --recv-keys 91A6E7F85D05C65630BEF18951852D87348FFC4C &&     mkdir -p /tmp/build &&     cd /tmp/build &&     wget ${HASHICORP_RELEASES}/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     wget ${HASHICORP_RELEASES}/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     wget ${HASHICORP_RELEASES}/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     grep ${DOCKER_BASE_VERSION}_linux_amd64.zip docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS | sha256sum -c &&     unzip docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     cp bin/gosu bin/dumb-init /bin &&     wget ${HASHICORP_RELEASES}/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip &&     wget ${HASHICORP_RELEASES}/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS &&     wget ${HASHICORP_RELEASES}/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify consul_${CONSUL_VERSION}_SHA256SUMS.sig consul_${CONSUL_VERSION}_SHA256SUMS &&     grep consul_${CONSUL_VERSION}_linux_amd64.zip consul_${CONSUL_VERSION}_SHA256SUMS | sha256sum -c &&     unzip -d /bin consul_${CONSUL_VERSION}_linux_amd64.zip &&     cd /tmp &&     rm -rf /tmp/build &&     apk del gnupg openssl &&     rm -rf /root/.gnupg
# Fri, 03 Mar 2017 21:46:44 GMT
RUN mkdir -p /consul/data &&     mkdir -p /consul/config &&     chown -R consul:consul /consul
# Fri, 03 Mar 2017 21:46:44 GMT
VOLUME [/consul/data]
# Fri, 03 Mar 2017 21:46:44 GMT
EXPOSE 8300/tcp
# Fri, 03 Mar 2017 21:46:45 GMT
EXPOSE 8301/tcp 8301/udp 8302/tcp 8302/udp
# Fri, 03 Mar 2017 21:46:45 GMT
EXPOSE 8400/tcp 8500/tcp 8600/tcp 8600/udp
# Fri, 03 Mar 2017 21:46:45 GMT
COPY file:de6c9a0e693ae46a375c565826f2071715281bba7f165975eb8537acd0d96ff4 in /usr/local/bin/docker-entrypoint.sh 
# Fri, 03 Mar 2017 21:46:46 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 03 Mar 2017 21:46:46 GMT
CMD ["agent" "-dev" "-client" "0.0.0.0"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:676ebc89eaf40d5605659e8ec38c6a21bfe22fc27f9e642d22ed913023ea8f6d`  
		Last Modified: Sat, 04 Mar 2017 04:35:23 GMT  
		Size: 1.3 KB (1270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90884291b44bce7481f57d3bee186d8c02f607ebb17fa09b2992c4d4706bf984`  
		Last Modified: Sat, 04 Mar 2017 04:35:27 GMT  
		Size: 10.6 MB (10590694 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:258a863da0c37cc345b6553390a51a534924017fbdcad0ae2318d72dbe4e27c1`  
		Last Modified: Sat, 04 Mar 2017 04:35:23 GMT  
		Size: 143.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a17c50c26b2fc84a38cfec9e0fbbbf4ade66c08a4ded028a202f9164bd00770f`  
		Last Modified: Sat, 04 Mar 2017 04:35:23 GMT  
		Size: 1.6 KB (1632 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `consul:0.7.5`

```console
$ docker pull consul@sha256:7fa3365242fca70d63e8e9737f4f1ac8687987d04bbdb7287bc80ea813e624ca
```

-	Platforms:
	-	linux; amd64

### `consul:0.7.5` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **12.9 MB (12907123 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b3dc6a88e25172c0006e6ef5512078fbc23c09d97cf4f10ab535821c83c46953`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["agent","-dev","-client","0.0.0.0"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 21:46:33 GMT
MAINTAINER James Phillips <james@hashicorp.com> (@slackpad)
# Fri, 03 Mar 2017 21:46:33 GMT
ENV CONSUL_VERSION=0.7.5
# Fri, 03 Mar 2017 21:46:33 GMT
ENV DOCKER_BASE_VERSION=0.0.4
# Fri, 03 Mar 2017 21:46:34 GMT
ENV HASHICORP_RELEASES=https://releases.hashicorp.com
# Fri, 03 Mar 2017 21:46:34 GMT
RUN addgroup consul &&     adduser -S -G consul consul
# Fri, 03 Mar 2017 21:46:43 GMT
RUN apk add --no-cache ca-certificates curl gnupg libcap openssl &&     gpg --recv-keys 91A6E7F85D05C65630BEF18951852D87348FFC4C &&     mkdir -p /tmp/build &&     cd /tmp/build &&     wget ${HASHICORP_RELEASES}/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     wget ${HASHICORP_RELEASES}/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     wget ${HASHICORP_RELEASES}/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     grep ${DOCKER_BASE_VERSION}_linux_amd64.zip docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS | sha256sum -c &&     unzip docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     cp bin/gosu bin/dumb-init /bin &&     wget ${HASHICORP_RELEASES}/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip &&     wget ${HASHICORP_RELEASES}/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS &&     wget ${HASHICORP_RELEASES}/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify consul_${CONSUL_VERSION}_SHA256SUMS.sig consul_${CONSUL_VERSION}_SHA256SUMS &&     grep consul_${CONSUL_VERSION}_linux_amd64.zip consul_${CONSUL_VERSION}_SHA256SUMS | sha256sum -c &&     unzip -d /bin consul_${CONSUL_VERSION}_linux_amd64.zip &&     cd /tmp &&     rm -rf /tmp/build &&     apk del gnupg openssl &&     rm -rf /root/.gnupg
# Fri, 03 Mar 2017 21:46:44 GMT
RUN mkdir -p /consul/data &&     mkdir -p /consul/config &&     chown -R consul:consul /consul
# Fri, 03 Mar 2017 21:46:44 GMT
VOLUME [/consul/data]
# Fri, 03 Mar 2017 21:46:44 GMT
EXPOSE 8300/tcp
# Fri, 03 Mar 2017 21:46:45 GMT
EXPOSE 8301/tcp 8301/udp 8302/tcp 8302/udp
# Fri, 03 Mar 2017 21:46:45 GMT
EXPOSE 8400/tcp 8500/tcp 8600/tcp 8600/udp
# Fri, 03 Mar 2017 21:46:45 GMT
COPY file:de6c9a0e693ae46a375c565826f2071715281bba7f165975eb8537acd0d96ff4 in /usr/local/bin/docker-entrypoint.sh 
# Fri, 03 Mar 2017 21:46:46 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 03 Mar 2017 21:46:46 GMT
CMD ["agent" "-dev" "-client" "0.0.0.0"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:676ebc89eaf40d5605659e8ec38c6a21bfe22fc27f9e642d22ed913023ea8f6d`  
		Last Modified: Sat, 04 Mar 2017 04:35:23 GMT  
		Size: 1.3 KB (1270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90884291b44bce7481f57d3bee186d8c02f607ebb17fa09b2992c4d4706bf984`  
		Last Modified: Sat, 04 Mar 2017 04:35:27 GMT  
		Size: 10.6 MB (10590694 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:258a863da0c37cc345b6553390a51a534924017fbdcad0ae2318d72dbe4e27c1`  
		Last Modified: Sat, 04 Mar 2017 04:35:23 GMT  
		Size: 143.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a17c50c26b2fc84a38cfec9e0fbbbf4ade66c08a4ded028a202f9164bd00770f`  
		Last Modified: Sat, 04 Mar 2017 04:35:23 GMT  
		Size: 1.6 KB (1632 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
