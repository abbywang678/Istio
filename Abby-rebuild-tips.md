The image in this repo is build with "Make"
The direct way to build the image is to use command "make docker.pilot", "make docker.proxyv2", then it will pull a build-tool image to compile the Go code to executable file.
But the build-tool image is in go 1.22 version, and we want to build go 1.23 to avoid future vuls.
So I use command "go build ~/istio/pilot/cmd/pilot-discovery", "go build ~/istio/pilot/cmd/pilot-agent" to generate executable file, and write it into the dockerfile to use docker to rebuild the image.
