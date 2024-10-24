The image in this repo is build with "Make".

The direct way to build the image is to use command "make docker.pilot", "make docker.proxyv2", then it will pull a build-tool image to compile the Go code to executable file and then build the image. 

But the build-tool image is in go 1.22 version, and we want to build go 1.23 to avoid future vuls. So I first use command “make istio-discovery” to generate the related file under new folder “out/linux_amd64”, and then use command "go build ~/istio/pilot/cmd/pilot-discovery", "go build ~/istio/pilot/cmd/pilot-agent" to generate executable file (istio-discovery and istio-agent) on the root path, and then write it into the dockerfile to use docker to rebuild the image.
