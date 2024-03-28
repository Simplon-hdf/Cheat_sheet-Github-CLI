# Installing gh on Linux and BSD
Packages downloaded from https://cli.github.com or from https://github.com/cli/cli/releases are considered official binaries. We focus on popular Linux distros and the following CPU architectures: i386, amd64, arm64, armhf.
Other sources for installation are community-maintained and thus might lag behind our release schedule.
## Official sources
Debian, Ubuntu Linux, Raspberry Pi OS (apt)
Install:
```
sudo mkdir -p -m 755 /etc/apt/keyrings && wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```
Install:
```
sudo apt update
sudo apt install gh 
``` 
Install from our package repository for immediate access to latest releases:
```
sudo dnf install 'dnf-command(config-manager)'
sudo dnf config-manager --add-repo https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh
```
