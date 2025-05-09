---
hide:
  - navigation
  - feedback
  - footer
---

> 如果觉得这个项目不错对您有所帮助的话，请点击仓库右上角的 Star 并分享给更多的朋友 :octicons-heart-fill-24:{ .heart style="color: red" }

!!! tip inline end "本项目脚本已被众多开源项目使用，广受社区用户好评"

## :simple-docker:{style="color: #1d63ed"} Docker 安装脚本

<table>
<tr>
    <td><a href="https://www.debian.org" target="_blank"><img src="/assets/images/icon/debian.svg" width="16" height="16" style="vertical-align: -0.35em"></a> Debian</td>
    <td><a href="https://access.redhat.com/products/red-hat-enterprise-linux" target="_blank"><img src="/assets/images/icon/redhat.svg" width="16" height="16" style="vertical-align: -0.1em"></a> Red Hat Enterprise Linux</td>
</tr>
<tr>
    <td><a href="https://cn.ubuntu.com" target="_blank"><img src="/assets/images/icon/ubuntu.svg" width="16" height="16" style="vertical-align: -0.15em"></a> Ubuntu</td>
    <td><a href="https://fedoraproject.org/zh-Hans" target="_blank"><img src="/assets/images/icon/fedora.ico" width="16" height="16" style="vertical-align: -0.2em"></a> Fedora</td>
</tr>
<tr>
    <td><a href="https://www.kali.org" target="_blank"><img src="/assets/images/icon/kali-linux.svg" width="16" height="16"></a> Kali Linux</td>
    <td><a href="https://www.centos.org" target="_blank"><img src="/assets/images/icon/centos.svg" width="16" height="16" style="vertical-align: -0.2em"></a> CentOS</td>
</tr>
<tr>
    <td><a href="https://linuxmint.com" target="_blank"><img src="/assets/images/icon/linux-mint.ico" width="16" height="16" style="vertical-align: -0.15em"></a> Linux Mint</td>
    <td><a href="https://rockylinux.org" target="_blank"><img src="/assets/images/icon/rocky-linux.svg" width="16" height="16" style="vertical-align: -0.25em"></a> Rocky Linux</td>
</tr>
<tr>
    <td><a href="https://www.deepin.org" target="_blank"><img src="/assets/images/icon/deepin.png" width="16" height="16" style="vertical-align: -0.3em"></a> Deepin（深度）</td>
    <td><a href="https://almalinux.org/zh-hans" target="_blank"><img src="/assets/images/icon/almalinux.svg" width="16" height="16" style="vertical-align: -0.15em"></a> AlmaLinux</td>
</tr>
<tr>
    <td><a href="https://zorin.com/os" target="_blank"><img src="/assets/images/icon/zorin-os.png" width="16" height="16" style="vertical-align: -0.3em"></a> Zorin OS</td>
    <td><a href="https://www.openeuler.org/zh" target="_blank"><img src="/assets/images/icon/openeuler.ico" width="16" height="16" style="vertical-align: -0.2em"></a> openEuler（开源欧拉）</td>
</tr>
<tr>
    <td><a href="https://www.armbian.com" target="_blank"><img src="/assets/images/icon/armbian.png" width="16" height="16" style="vertical-align: -0.2em"></a> Armbian</td>
    <td><a href="https://www.opencloudos.org" target="_blank"><img src="/assets/images/icon/opencloudos.png" width="16" height="16" style="vertical-align: -0.25em"></a> OpenCloudOS（鸥栖）</td>
</tr>
<tr>
    <td><a href="https://www.proxmox.com" target="_blank"><img src="/assets/images/icon/proxmox.svg" width="16" height="16" style="vertical-align: -0.2em"></a> Proxmox VE</td>
    <td><a href="https://openanolis.cn" target="_blank"><img src="/assets/images/icon/anolis.png" width="16" height="16" style="vertical-align: -0.1em"></a> Anolis OS（龙蜥）</td>
</tr>
<tr>
    <td><a href="https://www.raspberrypi.com" target="_blank"><img src="/assets/images/icon/raspberry-pi.png" width="16" height="16" style="vertical-align: -0.2em"></a> Raspberry Pi OS</td>
    <td></td>
</tr>
</table>

!!! quote ""

    === ":linuxmirrors: 官网（推荐）"

        ``` bash
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
        ```

    === ":simple-github: GitHub"

        ``` bash
        bash <(curl -sSL https://raw.githubusercontent.com/SuperManito/LinuxMirrors/main/DockerInstallation.sh)
        ```

    === ":simple-gitee: Gitee 码云"

        ``` bash
        bash <(curl -sSL https://gitee.com/SuperManito/LinuxMirrors/raw/main/DockerInstallation.sh)
        ```

    === ":simple-jsdelivr: jsDelivr（CDN）"

        ``` bash
        bash <(curl -sSL https://cdn.jsdelivr.net/gh/SuperManito/LinuxMirrors@main/DockerInstallation.sh)
        ```

集成安装 [`Docker Engine`](https://docs.docker.com/engine) 和 [`Docker Compose (插件)`](https://docs.docker.com/compose/install/linux)，支持选择或更换软件源以及镜像仓库、安装指定版本、重装等功能，支持 ARM 架构处理器

脚本参考 [官方文档](https://docs.docker.com/engine/install) 采用官方提供的方法使用系统包管理工具进行安装，这意味着可安装的版本是由官方仓库决定的，本脚本不存在兼容性等问题。

> 注：Docker Compose 自 V2 版本起开始作为 Docker CLI 的一部分，不再需要单独安装，请使用 `docker compose` 命令替代 `docker-compose`

!!! node "软件源说明"

    `Docker CE` 软件仓库，全称 Docker Community Edition（Docker 社区版），用于下载并安装 Docker 相关软件包  
    `Docker Registry` 镜像仓库，用于控制拉取镜像的默认来源存储仓库，又称镜像加速器，默认为官方的 Docker Hub 仓库

    由于一些不可抗力的因素，目前国内网络环境一般无法正常访问 Docker Hub 因此无法拉取镜像，使用推荐的镜像源勉强能够使用不过速度可能会很慢

- ### 命令选项（高级用法）

    <!-- termynal -->
    ```
    $ bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --help 

    命令选项(名称/含义/值)：

      --source                 指定 Docker CE 源地址(域名或IP)     地址
      --source-registry        指定镜像仓库地址(域名或IP)           地址
      --branch                 指定 Docker CE 源仓库(路径)         仓库名
      --codename               指定 Debian 系操作系统的版本代号     代号名称
      --designated-version     指定 Docker CE 安装版本             版本号
      --protocol               指定 Docker CE 源的 WEB 协议        http 或 https
      --install-latest         是否安装最新版本的 Docker Engine    true 或 false
      --close-firewall         是否关闭防火墙                      true 或 false
      --clean-screen           是否在运行前清除屏幕上的所有内容      true 或 false
      --ignore-backup-tips     忽略覆盖备份提示                    无
      --pure-mode              纯净模式，精简打印内容               无
    ```

    | 名称 | 含义 | 选项值 |
    | :-: | :-: | :-: |
    | `--source` | 指定 `Docker CE` 源地址(域名或IP) | `地址` |
    | `--source-registry` | 指定镜像仓库地址(域名或IP) | `地址` |
    | `--branch` | 指定 Docker CE 源仓库 | `仓库名（详见下方文档）` |
    | `--codename` | 指定 Debian 系操作系统的版本代号 | `代号名称` |
    | `--designated-version` | 指定 `Docker CE` 安装版本 | `版本号（详见下方文档）` |
    | `--protocol` | 指定 `Docker CE` 源的 WEB 协议 | `http` 或 `https` |
    | `--install-latest` | 是否安装最新版本的 Docker Engine | `true` 或 `false` |
    | `--close-firewall` | 是否关闭防火墙 | `true` 或 `false` |
    | `--clean-screen` | 是否在运行前清除屏幕上的所有内容 | `true` 或 `false` |
    | `--ignore-backup-tips` | 忽略覆盖备份提示（即不覆盖备份） | 无 |
    | `--pure-mode` | 纯净模式，精简打印内容 | 无 |

    > 软件源完整格式 `<WEB协议>://<软件源地址(域名或IP)>/<软件源仓库(路径)>`

    - #### 指定 Docker CE 软件源地址

        ``` { .bash .no-copy }
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --source mirror.example.com/docker-ce
        ```
        > 注意该地址路径需要包含镜像站的 Docker CE 软件源仓库路径即 `docker-ce`

    - #### 指定镜像仓库地址

        ``` { .bash .no-copy }
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --source-registry registry.example.com
        ```

    - #### 指定 Docker CE 软件源仓库

        脚本默认会自动判断一般无需指定，除非你有特殊需求

        ``` { .bash .no-copy }
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --branch centos
        ```
        > 仓库名是固定的，目前只有 `centos` `debian` `fedora` `raspbian` `rhel` `sles` `static` `ubuntu` 这几个  
        > 具体详见 [官方安装文档](https://docs.docker.com/engine/install) 和 [Docker CE 官方仓库](https://download.docker.com/linux)

    - #### 指定 Docker CE 安装版本

        指定安装版本时会忽略 `是否安装最新版本` 的命令选项，格式为 `主版本.次版本.补丁版本`，例如 `27.4.1`。

        ``` { .bash .no-copy }
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --designated-version 27.0.0
        ```
        > 如果指定的版本不存在或者不支持当前系统，届时脚本会报错跳出

        ??? quote "查看版本列表的方法"

            === "Debian 系"

                ``` bash
                apt-cache madison docker-ce | awk '{print $3}' | grep -Eo "[0-9][0-9].[0-9]{1,2}.[0-9]{1,2}" | sort -t '.' -k1,1nr -k2,2nr -k3,3nr
                ```

                > `Debian` &nbsp; `Ubuntu` &nbsp; `Kali` &nbsp; `Linux Mint` &nbsp; `Deepin` &nbsp; `Zorin OS` &nbsp; `Armbian` &nbsp; `Proxmox VE` &nbsp; `Raspberry Pi OS`

            === "RedHat 系 / openEuler / OpenCloudOS / Anolis OS"

                ``` bash
                dnf list docker-ce --showduplicates | sort -r | awk '{print $2}' | grep -Eo "[0-9][0-9].[0-9]{1,2}.[0-9]{1,2}" | sort -t '.' -k1,1nr -k2,2nr -k3,3nr
                ```

                > `Red Hat Enterprise Linux` &nbsp; `CentOS` &nbsp; `Rocky Linux` &nbsp; `AlmaLinux` &nbsp; `Fedora` &nbsp; `openEuler` &nbsp; `OpenCloudOS` &nbsp; `Anolis OS`

            未出现在该列表中的版本则不支持通过本脚本安装，如果获取不到版本列表说明你当前的系统环境还没有正确配置 Docker CE 软件源（运行脚本时不存在该问题）


    - #### 无人值守（自动化）

        不通过交互完成安装操作，至少需要使用如下命令选项来实现，建议熟悉后再使用

        ``` { .bash .no-copy title="参考命令" }
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh) \
          --source mirror.example.com/docker-ce \
          --source-registry registry.hub.docker.com \
          --protocol http \
          --use-intranet-source false \
          --install-latest true \
          --close-firewall true \
          --ignore-backup-tips
        ```
        > 如果报错 `命令选项无效` 那么请检查选项合法性以及空格字符编码，示例中选项一行写一个是为了提高阅读性

    - #### 纯净模式

        为了便于开发者使用故推出此功能，启用后会精简脚本内容输出，建议搭配其它命令选项无交互使用

        ``` bash
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --pure-mode
        ```

        !!! tip "滚动输出的命令日志可能存在无法预料的显示问题，不过目前暂未发现异常"

- ### 关于服务报错无法启动

    !!! quote ""

        非新装环境可能会在运行脚本后遇到 `Docker` 服务无法启动的情况，建议重新安装来解决，卸载不会删除本地镜像和容器数据

        卸载命令如下：

        === "Debian 系"

            ``` bash
            apt-get remove -y docker* containerd.io runc && apt-get autoremove
            ```

            > `Debian` &nbsp; `Ubuntu` &nbsp; `Kali` &nbsp; `Linux Mint` &nbsp; `Deepin` &nbsp; `Zorin OS` &nbsp; `Armbian` &nbsp; `Proxmox VE` &nbsp; `Raspberry Pi OS`

        === "RedHat 系 / openEuler / OpenCloudOS / Anolis OS"

            ``` bash
            yum remove -y docker* containerd.io podman* runc
            ```

            > `Red Hat Enterprise Linux` &nbsp; `CentOS` &nbsp; `Rocky Linux` &nbsp; `AlmaLinux` &nbsp; `Fedora` &nbsp; `openEuler` &nbsp; `OpenCloudOS` &nbsp; `Anolis OS`

        卸载完成后重新执行脚本安装即可
