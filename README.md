# systemConfigs

Steps for setting up a new Mac

## File Vault Setup

- Enable in System Preferences

## Homebrew Setup

### Install

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Turn off analytics

```
brew analytics off
```

### Brewfile Setup

- move `Brewfile` from [systemConfigs/Brewfile](https://github.com/mattgrieser/systemConfigs/blob/main/Brewfile) to `~/Brewfile` on machine.

#### Install Brewfile

```
brew bundle install
```

## OhMyZsh Setup

### Update zshrc

- move `.zshrc` from [systemConfigs/zshrc](https://github.com/mattgrieser/systemConfigs/blob/main/.zshrc) to `~/.zshrc`on machine.

## ClamAV Setup

### Make Directory

```
sudo mkdir /usr/local/sbin
```

### Update Permissions

```
sudo chown -R `whoami`:admin /usr/local/sbin
```

### Link

```
brew link clamav
```

### Move to Directory

```
cd /usr/local/etc/clamav/
```

### Copy Configuration File

```
cp freshclam.conf.sample freshclam.conf
```

### Copy Example Config

```
sed -ie 's/^Example/#Example/g' freshclam.conf
```

### Update Listings

```
freshclam -v
```

### Scan Only

- run weekly

```
clamscan -r -i 
```

### Scan and Remove

- run weekly

```
clamscan -i -r --remove=yes /
```

## Task Explorer

- Run weekly

## KnockKnock

- run weekly

## Oversight

- might need to install older version from site

## Karibiner Elements

- Set up caps lock > hyper key once installed

## Obsidian

- Sync vault from obsidian sync once installed

## Update Homebrew Weekly

%%unsure on all these steps with brew cu doing some of the lift%%

```
brew cu --include-mas

brew update

brew upgrade

brew cleanup -s

brew autoremove

brew doctor
```

## Mac Settings

- Set up hot corners
- Move dock to left and hiding on
- Safari show favorites bar
- Update terminal appearance defaults

## Run Privacy Script Weekly

- [privacy.sexy](https://privacy.sexy)
