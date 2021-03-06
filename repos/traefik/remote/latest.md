## `traefik:latest`

```console
$ docker pull traefik@sha256:0c40960d4b0252c727cd005bb242156b5db84ac75317d29f252d015ff7af7491
```

-	Platforms:
	-	linux; amd64

### `traefik:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **11.6 MB (11634847 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0422f4e3424d6de7e4885a8cfe4b03754589e67970466db8b3c4361e63c9c892`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Thu, 15 Dec 2016 17:54:02 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Mon, 27 Mar 2017 19:54:29 GMT
COPY file:6f46e3a1e5f11c1871d01b6a84c8dbb691e573e8cc48619f6a98538f0e5c063d in / 
# Mon, 27 Mar 2017 19:54:30 GMT
EXPOSE 80/tcp
# Mon, 27 Mar 2017 19:54:30 GMT
ENTRYPOINT ["/traefik"]
# Mon, 27 Mar 2017 19:54:31 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.2.1 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:03a84e30597f6e498aa09e940b69f623d31c22909fa05c7132e1b142f9439e38`  
		Last Modified: Thu, 15 Dec 2016 17:54:23 GMT  
		Size: 156.1 KB (156143 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50b178731bbb47b96cd00e85769a8a4fb1a6e86790530a0fc3cd1264a4c6e493`  
		Last Modified: Mon, 27 Mar 2017 19:55:08 GMT  
		Size: 11.5 MB (11478704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
