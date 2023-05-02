FROM ubuntu:22.04

RUN set -e; \
        apt update; \
	apt upgrade -y; \
        :

# Install packages
RUN DEBIAN_FRONTEND=noninteractive apt install -y \
	wget squashfs-tools build-essential git dosfstools \
	e2fsprogs parted sudo mtools p7zip p7zip-full \
	device-tree-compiler acpica-tools u-boot-tools \
	e2tools libssl-dev cpio rsync bc bison flex \
	python2 unzip python3 zlib1g-dev udev cmake \
	libusb-1.0-0 bzip2 libbz2-dev libbz2-1.0 \
	libusb-1.0-0-dev libzip-dev pkg-config g++ \
	vim qemu-system-arm libtool m4 automake meson \
        python3-pip fdisk kmod cloud-utils \
        libelf-dev

#        pkg-config-aarch64-linux-gnu python3-pip


# Install python packages
RUN pip3 install pyelftools

# Set workdir
WORKDIR /cn913x_build_dir


# Build arguments, username and user id
#ARG user
#ARG userid

# If user passed no arguments, exit with an error
#RUN if [ -z "$user" ]; then printf "\n\nPlease pass the user argument\n\n"; exit -1; fi

#RUN if [ -z "$userid" ]; then printf "\n\nPlease pass the userid argument\n\n"; exit -1; fi

# Add user
#RUN useradd -u $userid $user

# Run as user
#USER $user
RUN git config --global user.name cnbuild
RUN git config --global user.email cnbuild

RUN ln -s /usr/bin/python2 /usr/bin/python
