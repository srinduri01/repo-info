## `mono:latest`

```console
$ docker pull mono@sha256:172638c84b44ae1902bc5264011d854e62d71eedb7435c985c5b03f8bcbb6605
```

-	Platforms:
	-	linux; amd64

### `mono:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **144.7 MB (144700027 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:eefe8a74dfd797d392a2be8b5a066bda3750a69630de170660122ab780288fe9`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 21 Mar 2017 18:36:18 GMT
ADD file:460db8bc0a8ce517fff9d1dc4f7d1e238fc55a11e80c4d09a36cc01ed7372733 in / 
# Tue, 21 Mar 2017 18:36:19 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 21:03:02 GMT
MAINTAINER Jo Shields <jo.shields@xamarin.com>
# Tue, 21 Mar 2017 21:11:04 GMT
ENV MONO_VERSION=4.8.0.495
# Tue, 21 Mar 2017 21:11:14 GMT
RUN apt-get update   && apt-get install -y curl   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 21:11:16 GMT
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
# Tue, 21 Mar 2017 21:12:36 GMT
RUN echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots/$MONO_VERSION main" > /etc/apt/sources.list.d/mono-xamarin.list   && apt-get update   && apt-get install -y binutils mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl   && rm -rf /var/lib/apt/lists/* /tmp/*
```

-	Layers:
	-	`sha256:1963618b459343af38baedd65fb15049a4c76f8c75458ea2974cdcda1fa7cd9b`  
		Last Modified: Tue, 21 Mar 2017 18:52:57 GMT  
		Size: 37.3 MB (37271836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0d4e4c2fc8b0d8430255135386f9f4bfd497fb8de5d9b8c4834077a0e9824f4`  
		Last Modified: Thu, 23 Mar 2017 22:48:06 GMT  
		Size: 7.6 MB (7647023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d016b2e35bace59358e858b4890fb9301b0d60b6ffd1b947d9680d46d5048de`  
		Last Modified: Thu, 23 Mar 2017 22:48:03 GMT  
		Size: 29.9 KB (29901 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:93517eae7f6120fa275a5fd12c3a572efd8b727bdbf7e281ee5208f619b7456a`  
		Last Modified: Thu, 23 Mar 2017 22:48:38 GMT  
		Size: 99.8 MB (99751267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
