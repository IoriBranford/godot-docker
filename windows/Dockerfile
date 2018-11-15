FROM tianon/wine:64
MAINTAINER IoriBranford <ioribranford@gmail.com>

ARG GODOT_VERSION=3.0.6
ARG GODOT_VARIANT=stable
ARG RCEDIT_VERSION=1.1.1

RUN echo "ipv6" >> /etc/modules \
    && apt-get update -q \
    && apt-get install -yq wget unzip zip \
    && wget \
"http://download.tuxfamily.org/godotengine/${GODOT_VERSION}/Godot_v${GODOT_VERSION}-${GODOT_VARIANT}_linux_headless.64.zip" \
"http://downloads.tuxfamily.org/godotengine/${GODOT_VERSION}/Godot_v${GODOT_VERSION}-${GODOT_VARIANT}_export_templates.tpz" \
"https://github.com/electron/rcedit/releases/download/v${RCEDIT_VERSION}/rcedit-x64.exe" \
    && unzip Godot_v*_linux_headless.64.zip \
    && mv Godot_v*_linux_headless.64 /bin/godot \
    && mkdir -p ~/.local/share/godot/templates \
    && unzip Godot_v*_export_templates.tpz \
    && mv templates/ ~/.local/share/godot/templates/${GODOT_VERSION}.${GODOT_VARIANT}/ \
    && chmod +x rcedit-x64.exe \
    && mv rcedit-x64.exe /bin \
    && rm -f *.zip *.tpz

RUN mkdir -p ~/.cache && mkdir -p ~/.config/godot
