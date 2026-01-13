# Installation Guide For Kubernetes On Ubuntu 24.04.3 LTS

## 1. Installing Rancher desktop

```bash
curl -s https://download.opensuse.org/repositories/isv:/Rancher:/stable/deb/Release.key | gpg --dearmor | sudo dd status=none of=/usr/share/keyrings/isv-rancher-stable-archive-keyring.gpg

echo 'deb [signed-by=/usr/share/keyrings/isv-rancher-stable-archive-keyring.gpg] https://download.opensuse.org/repositories/isv:/Rancher:/stable/deb/ ./' | sudo dd status=none of=/etc/apt/sources.list.d/isv-rancher-stable.list

sudo apt update

sudo apt install rancher-desktop
```

## 2. Installing k9s

```bash
# Install latest version
curl -sS https://webinstall.dev/k9s | bash
```

## 3. After the installation, this appears in the terminal:

```
Installed 'k9s v0.50.16' as ~/.local/bin/k9s

    Edit ~/.config/envman/PATH.env to add:
        ~/.local/bin

>>> ACTION REQUIRED <<<

    Copy, paste & run the following command:
    source ~/.config/envman/PATH.env
    (newly opened terminal windows will update automatically)
```

## 4. Run this command to add path so you can run k9s from anywhere

```bash
source ~/.config/envman/PATH.env
```

## 5. Check if k9 is now accesible by running

```bash
k9s version
```

## 6. Since you're using bash, add this to the shell startup file

```bash
echo 'source ~/.config/envman/PATH.env' >> ~/.bashrc
```

## 7. Check if k9 is installed successfully

```bash
k9s
```
