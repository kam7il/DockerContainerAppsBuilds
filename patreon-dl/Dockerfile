FROM node:23-alpine

WORKDIR /app

# install FFmpeg
RUN apk update && \
	apk add ffmpeg && \
	apk add git && \
	git clone --depth 1 https://github.com/patrickkfkan/patreon-dl.git ./patreon-dl && \
	cd ./patreon-dl && \
	npm i -g patreon-dl

# ENTRYPOINT ["/bin/sh"]
# docker run --rm -it --volume /DockerMounts/patreon-dl:/download patreon-dl

ENTRYPOINT ["patreon-dl","--no-prompt"]
CMD ["--help"]

# docker run --rm --name patreon-dl -v /DockerMounts/patreon-dl:/download patreon-dl -c "cookie" --out-dir /download "https://www.patreon.com/c/USER/posts"
