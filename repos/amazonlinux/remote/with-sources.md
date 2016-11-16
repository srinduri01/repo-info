## `amazonlinux:with-sources`

```console
$ docker pull amazonlinux@sha256:ac093c01bb89f8e70d537d5698ccabb30bbb26e26d79675f2cf101fad483a075
```

-	Platforms:
	-	linux; amd64

### `amazonlinux:with-sources` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **406.3 MB (406273032 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:445e25892f47aa99b0c0f5f3f70511bf596e5cae23b6e9263dfd790c71afcc2c`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Wed, 16 Nov 2016 00:37:25 GMT
ADD file:0c65dc52d4db4a2177e7e9adb829baceae20c73a9f42678d1074ad76ac0b88f7 in / 
# Wed, 16 Nov 2016 00:37:26 GMT
CMD ["/bin/bash"]
# Wed, 16 Nov 2016 00:37:55 GMT
RUN curl -o /usr/src/srpm/srpm-bundle.tar.gz "https://s3.amazonaws.com/amazon-linux-docker-sources/srpm-bundle.tar.gz?versionId=BOOVw_RRxOLMdMbXgFnUSdgn8dTyVN17"  && echo "22647c2c901a0cd8f516e095fcf5752256e5497bbbf2205fbe5ad19d53fb0193 /usr/src/srpm/srpm-bundle.tar.gz" | sha256sum -c -
```

-	Layers:
	-	`sha256:67b04f48477e3b98865487ba55d354c019bbd180ba89c16dbb0b305213ad1e2b`  
		Last Modified: Wed, 16 Nov 2016 00:38:43 GMT  
		Size: 101.6 MB (101595959 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89708912ed5c75089553f7b3a67cf51b5b9353ff858837d5b01c523b8c4aee14`  
		Last Modified: Wed, 16 Nov 2016 00:39:47 GMT  
		Size: 304.7 MB (304677073 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip