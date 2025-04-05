FROM node:23-alpine

WORKDIR /app

# install FFmpeg
RUN apk update && \
	apk add ffmpeg && \
	apk add git && \
	git clone --depth 1 https://github.com/patrickkfkan/patreon-dl.git ./patreon-dl && \
	cd ./patreon-dl && \
	npm i -g patreon-dl
	
ENTRYPOINT ["/bin/sh"]

# RUN DOCKER
# docker run --rm -it --volume /DockerMounts/patreon-dl:/download patreon-dl
