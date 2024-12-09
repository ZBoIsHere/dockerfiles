# make sure the host drivers >= cuda11.7.1 corresponding version
FROM nvidia/cuda:11.7.1-devel-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

# Setup time zone and locale data (necessary for SSL and HTTPS packages)
RUN apt-get update && DEBIAN_FRONTEND="noninteractive" apt-get install --no-install-recommends -y \
    wget \
    bzip2 \ 
    libfreetype6 \
    libgl1-mesa-dev \
    libglu1-mesa \
    libxi6 \ 
    libxrender1 \
    xz-utils \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

ENV BLENDER_MAJOR 2.93
ENV BLENDER_VERSION 2.93.18
ENV BLENDER_TAR_URL https://download.blender.org/release/Blender${BLENDER_MAJOR}/blender-${BLENDER_VERSION}-linux-x64.tar.xz

RUN mkdir /usr/local/blender && \
	wget ${BLENDER_TAR_URL} -O blender.tar.xz && \
	tar -xvf blender.tar.xz -C /usr/local/blender --strip-components=1 && \
	rm blender.tar.xz

#ENTRYPOINT ["/usr/local/blender/blender", "-b"]
