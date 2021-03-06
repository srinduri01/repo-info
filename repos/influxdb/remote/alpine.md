## `influxdb:alpine`

```console
$ docker pull influxdb@sha256:048c1d9afc0eb2ef499f1697d6197a6af3fb0f7450fb8c8e552c521a768c3518
```

-	Platforms:
	-	linux; amd64

### `influxdb:alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.1 MB (14139711 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:61273580599e3e1ea4ed9e3ca2878589bb73cf8d3dd5d288983b555199c70dd3`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["influxd"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:37 GMT
ADD file:730030a984f5f0c5dc9b15ab61da161082b5c0f6e112a9c921b42321140c3927 in / 
# Wed, 15 Mar 2017 21:31:45 GMT
ENV INFLUXDB_VERSION=1.2.2
# Wed, 15 Mar 2017 21:31:53 GMT
RUN apk add --no-cache --virtual .build-deps wget gnupg tar ca-certificates &&     update-ca-certificates &&     gpg --keyserver hkp://ha.pool.sks-keyservers.net         --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5 &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz.asc influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src &&     tar -C /usr/src -xzf influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     rm -f /usr/src/influxdb-*/influxdb.conf &&     chmod +x /usr/src/influxdb-*/* &&     cp -a /usr/src/influxdb-*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Wed, 15 Mar 2017 21:31:54 GMT
COPY file:3ee2bc0321c2aa2451df7a508649c3a54f0eebc1ef9b8a24967c58105b4d3160 in /etc/influxdb/influxdb.conf 
# Wed, 15 Mar 2017 21:31:54 GMT
EXPOSE 8086/tcp
# Wed, 15 Mar 2017 21:31:55 GMT
VOLUME [/var/lib/influxdb]
# Wed, 15 Mar 2017 21:31:55 GMT
COPY file:69ba622c5d14acee69909e208de64bf13aa81f0010ff82238c8825ba99d65290 in /entrypoint.sh 
# Wed, 15 Mar 2017 21:31:56 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 15 Mar 2017 21:31:56 GMT
CMD ["influxd"]
```

-	Layers:
	-	`sha256:627beaf3eaaff1c0bc3311d60fb933c17ad04fe377e1043d9593646d8ae3bfe1`  
		Last Modified: Fri, 03 Mar 2017 20:34:41 GMT  
		Size: 1.9 MB (1905270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:975c55395dc185517cd97ec6ae711d8a0aaee0279e3a4aab944ed1c2ca355ca5`  
		Last Modified: Wed, 15 Mar 2017 21:35:31 GMT  
		Size: 12.2 MB (12234035 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aff2bdab784746ace0c34609fa93cd3e80a319e8cb0b7758de422f913d3d2bb7`  
		Last Modified: Wed, 15 Mar 2017 21:35:24 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb02ad705c0a12bb193667969fd55a06bb7411d1c5ee15735016cbb496f7c33e`  
		Last Modified: Wed, 15 Mar 2017 21:35:24 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
