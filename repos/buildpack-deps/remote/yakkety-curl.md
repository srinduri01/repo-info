## `buildpack-deps:yakkety-curl`

```console
$ docker pull buildpack-deps@sha256:3ec43c9967df87c5a5e55ab59bd8fb2a6bbd9a087ebfa9ddb2bdf0ee4c33c3a5
```

-	Platforms:
	-	linux; amd64

### `buildpack-deps:yakkety-curl` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **48.0 MB (47992540 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5066a4e9cb1daddb1861feebb1c0140de595d913186500808303c3ffe69fd92c`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 27 Feb 2017 19:42:31 GMT
ADD file:e741da914b6b0133690befb4d6db33aec2f792f002095a35426bf4831265e309 in / 
# Mon, 27 Feb 2017 19:42:42 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 27 Feb 2017 19:42:43 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 27 Feb 2017 19:42:44 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 27 Feb 2017 19:42:59 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 27 Feb 2017 19:43:00 GMT
CMD ["/bin/bash"]
# Mon, 27 Feb 2017 21:32:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
```

-	Layers:
	-	`sha256:d3d3b7c0d7792f1b412cee8427783baaf5e8fb8f1846e6a6c2452150278bf286`  
		Last Modified: Mon, 27 Feb 2017 19:51:10 GMT  
		Size: 41.1 MB (41123164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca51f5907d7b054b0ef55618f22dcf09c7977044da3da307d6500624c69eced0`  
		Last Modified: Mon, 27 Feb 2017 19:50:58 GMT  
		Size: 824.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:903bbd903b1fa548c5dc42e2e895ef6bed80f98d0881b157cd91d59a999587ce`  
		Last Modified: Mon, 27 Feb 2017 19:50:59 GMT  
		Size: 519.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bb21db247f02fd7a2e31c3827462bd15066a64287f3a5e1f6039bb9a139275a`  
		Last Modified: Mon, 27 Feb 2017 19:50:58 GMT  
		Size: 862.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c8271917b11cce060218803c76f41293f3d126ce5dc6ef44f069d1ff34297b9`  
		Last Modified: Mon, 27 Feb 2017 19:50:59 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7580a8280f2e9442e395867af88b303881f8d59675f2a5cad7204069d85a657d`  
		Last Modified: Mon, 27 Feb 2017 22:09:33 GMT  
		Size: 6.9 MB (6867009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
