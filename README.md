# MacOS-configuration
- [Macintosh](#macintosh)
    - [1.使NTFS格式的硬盘（DATA）可写](#1使ntfs格式的硬盘data可写)
    - [2.homebrew](#2homebrew)
    - [3.oh-my-zsh](#3oh-my-zsh)
      - [3.1 autojump](#31-autojump)
      - [3.2 autosuggestions](#32-autosuggestions)
    - [4.疑难杂症](#4疑难杂症)
      - [4.1 curl: (7) Failed to connect to raw.githubusercontent.com port 443: Connection refused](#41-curl-7-failed-to-connect-to-rawgithubusercontentcom-port-443-connection-refused)
      - [4.2 unavailable: error executing an http request: libcurl code 35 meaning 'ssl connect error', error details: server aborted the ssl handshake](#42-unavailable-error-executing-an-http-request-libcurl-code-35-meaning-ssl-connect-error-error-details-server-aborted-the-ssl-handshake)
    - [5. 修改](#5-修改)
# Macintosh

### 1.使NTFS格式的硬盘（DATA）可写

使用`diskutil  list`查看你要修改的盘名

```shell
sudo nano /etc/fstab
```

添加：`LABEL=DATA none ntfs rw,auto,nobrowse`

CTRL + X保存，选择 Y，然后按回车键，重启之后DATA就可写了。

### 2.homebrew

```shell
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

### 3.oh-my-zsh

```shell
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

#### 3.1 autojump

```shell
brew install autojump
```

#### 3.2 autosuggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### 4.疑难杂症

#### 4.1 curl: (7) Failed to connect to raw.githubusercontent.com port 443: Connection refused

在本机的 host 文件中添加，建议使用 [switchhosts](https://github.com/oldj/SwitchHosts/releases) 方便 host 管理

199.232.68.133 raw.githubusercontent.com
199.232.68.133 user-images.githubusercontent.com
199.232.68.133 avatars2.githubusercontent.com
199.232.68.133 avatars1.githubusercontent.com

#### 4.2 unavailable: error executing an http request: libcurl code 35 meaning 'ssl connect error', error details: server aborted the ssl handshake

-

### 5. 修改

