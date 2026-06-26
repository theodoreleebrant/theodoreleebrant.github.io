Figured that I should document what I need in a fresh installation of Ubuntu; this has been a thing for many years but I just never gotten to doing it because forgor :)

Now I'm setting up the work PC using Ubuntu, so hope this goes well (and that I update this post)

Update (26 June 2026): I have had the (dis)pleasure of setting up two more personal machines, so here goes:

```
sudo -v
sudo apt update
sudo apt install -y ca-certificates curl wget gnupg software-properties-common
sudo add-apt-repository -y -n multiverse && sudo add-apt-repository -y -n ppa:linrunner/tlp
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo tee /etc/apt/keyrings/sublimehq-pub.asc > /dev/null
echo -e 'Types: deb\nURIs: https://download.sublimetext.com/\nSuites: apt/stable/\nSigned-By: /etc/apt/keyrings/sublimehq-pub.asc' | sudo tee /etc/apt/sources.list.d/sublime-text.sources > /dev/null
sudo apt update
sudo apt install -y vim curl wget git htop tmux tree jq unzip zip rsync net-tools dnsutils traceroute tcpdump nmap lsof ripgrep ncdu btop texlive-full sublime-text sublime-merge flatpak gnome-software-plugin-flatpak gnome-shell-extension-manager smbclient python3-smbc gimp tlp
sudo apt install -y ttf-mscorefonts-installer
sudo snap install telegram-desktop slack discord spotify obsidian
sudo snap install code --classic
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo && flatpak install -y flathub io.github.focustimerhq.FocusTimer
curl -fsSL https://tailscale.com/install.sh | sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
sudo systemctl enable --now tlp
sudo tailscale up
git --version; vim --version | head -n 1; code --version | head -n 1; tailscale version; rustc --version; cargo --version
```
