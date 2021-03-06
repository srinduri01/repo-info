<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `hello-world`

-	[`hello-world:latest`](#hello-worldlatest)
-	[`hello-world:nanoserver`](#hello-worldnanoserver)

## `hello-world:latest`

```console
$ docker pull hello-world@sha256:c5515758d4c5e1e838e9cd307f6c6a0d620b5e07e6f927b07d05f6d12a1ac8d7
```

-	Platforms:
	-	linux; amd64

### `hello-world:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **971.0 B**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:48b5124b2768d2b917edcb640435044a97967015485e812545546cbed5cf0233`
-	Default Command: `["\/hello"]`

```dockerfile
# Fri, 13 Jan 2017 22:50:55 GMT
COPY file:22b680a46dca706cf95f38d1f17b22bcaf396780b37fc67b8789dfb924616ed8 in / 
# Fri, 13 Jan 2017 22:50:56 GMT
CMD ["/hello"]
```

-	Layers:
	-	`sha256:78445dd45222097f5f8d5a16e48dc19c4ca162dcdb80010ab6f1ccfc7e2c0fa3`  
		Last Modified: Fri, 13 Jan 2017 22:51:11 GMT  
		Size: 971.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `hello-world:nanoserver`

```console
$ docker pull hello-world@sha256:25eac12ba40f7591969085ab3fb9772e8a4307553c14ea72d0e6f98b2c8ced9d
```

-	Platforms:
	-	windows; amd64

### `hello-world:nanoserver` - windows; amd64

-	Docker Version: 1.12.2-cs2-ws-beta
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **333.3 MB (333311291 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:aa8467f01b47cc23e5553f939176241d83894f12760dc62163a9167ea29bed4d`
-	Default Command: `["cmd","\/C","type C:\\hello.txt"]`

```dockerfile
# Sat, 14 Jan 2017 00:13:02 GMT
RUN cmd /S /C #(nop) COPY file:a5052dbb0d93d3999b3ee937f847dbf9005dbd46508351d1f4316fe2f9adef71 in C: 
# Sat, 14 Jan 2017 00:13:04 GMT
RUN cmd /S /C #(nop)  CMD ["cmd" "/C" "type C:\\hello.txt"]
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:3ac17e2e6106d09a44642a437c318092eddd284afea0b4e707e89f6cec7a18ef`  
		Size: 80.6 MB (80617684 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:8cac44e17f163c3d91ed53f581567737c54e14356bfddfe2335118af67647055`  
		Last Modified: Sat, 14 Jan 2017 00:13:09 GMT  
		Size: 1.7 KB (1652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e160e4d8db328496619b49dde96716f1fe35baa7eebe3798b41130309de8105`  
		Last Modified: Sat, 14 Jan 2017 00:13:08 GMT  
		Size: 953.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
