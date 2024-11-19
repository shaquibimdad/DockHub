FROM archlinux

# Install required packages and clean cache
RUN pacman -Sy --needed --noconfirm base base-devel fish git curl unzip zip ccache rsync tree neofetch \
    nano htop jq android-udev make tmux vi sudo stow \
    && pacman -Scc --noconfirm

# Fish shell configuration
RUN mkdir -p /etc/skel/.config/fish \
    && echo 'set -U fish_greeting' > /etc/skel/.config/fish/config.fish && echo "android ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Install mise globally
ENV MISE_DATA_DIR=/usr/local/share/mise
RUN curl https://mise.run | MISE_INSTALL_PATH=/usr/local/bin/mise sh \
    && echo '/usr/local/bin/mise activate fish | source' >> /etc/skel/.config/fish/config.fish

# Install global tools with mise
RUN mise use --global node@20 \
    && mise use --global java@openjdk-17 \
    && mise use --global python@3.12

ENV JAVA_HOME=/usr/local/share/mise/installs/java/openjdk-17

# Add yarn globally
ENV PATH=/usr/local/share/mise/installs/node/20/bin:${PATH}
RUN npm install -g yarn

RUN useradd -m -u 1000 -s /usr/bin/fish android

USER android

# Install global tools with mise
RUN mise use --global node@20 \
    && mise use --global java@openjdk-17 \
    && mise use --global python@3.12

WORKDIR /home/android