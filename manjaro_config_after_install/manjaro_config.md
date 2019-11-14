# manjaro安装后配置
### 卸载不需要的软件

    sudo pacman -Rcnsu steam-manjaro
    sudo pacman -Rcnsu firefox
    sudo pacman -Rcnsu thunderbird
    sudo pacman -Rcnsu konversation

### 更换中国镜像源

    sudo pacman-mirrors -i -c China -m rank
    
出现图形界面选择任意源点击确定（OK）。  
然后同步并更新

    sudo pacman -Syyu

### 安装中文输入法
##### 安装字体

    sudo pacman -S adobe-source-han-sans-cn-fonts adobe-source-han-serif-cn-fonts

##### 安装google拼音和fcitx工具

    sudo pacman -S fcitx fcitx-googlepinyin fcitx-im fcitx-configtool

##### 配置
* 编辑文件~/.xprofile（如果没有的话就新建一个）
    ```
    sudo vim ~/.xprofile
    ```
* 在其中添加（写入）如下信息：
    ```
    export GTK_IM_MODULE=fcitx
    export QT_IM_MODULE=fcitx
    export XMODEFIERS="@im=fcitx"
    ```

### 安装yay工具

    sudo pacman -S yay

### 安装必要的软件

##### 安装vim

    yay -S vim
因为我习惯spacevim来配置,所以这里就只介绍spacevim的简单安装与配置  
* 安装spacevim
    ```
    curl -sLf https://spacevim.org/install.sh | bash
    ```
* 打开vim，开始自动安装插件
* 安装完插件之后，退出vim，编辑家目录下生成的`~/.Spacevim.d/init.toml`文件
    ```
    vim ~/.Spacevim.d/init.toml
    ```
    具体的配置就参考spacevim的[官网](https://spacevim.org/quick-start-guide/)啦。


##### 安装aria2终端下载工具
    yay -S aria2

##### 安装vscode
    yay -S visual-studio-code-bin

##### 安装谷歌浏览器
    yay -S google-chrome

##### 安装v2ray
    yay -S v2ray
    
##### 安装privoxy，manjaro下需要使用该工具配置后才可科学上网
    yay -S privoxy
    
* privoxy配置
    * 编辑`/etc/privoxy/config`，添加socks5转发
        ```
        forward-socks5 / 127.0.0.1:1080
        ```
    * 设置privoxy开机启动，重启privoxy服务
        ```
        sudo systemctl enable privoxy.service
        sudo systemctl restart privoxy.service

##### 安装proxychains用于终端科学上网
    yay -S proxychains-ng

* proxychains配置
    
    编辑/etc/proxychains.conf,修改最后一行为`soks5 127.0.0.1 1080`，即

    ```
    socks4 127.0.0.1 9050
    ```

    &emsp; &emsp; &emsp; &emsp; &emsp; &emsp;&dArr;

    ```
    socks5 127.0.0.1 1080
    ```

##### 安装网易云音乐

    yay -S netease-cloud-music

如果安装时出现错误不能安装（我就遇到了〒▽〒）  
那么就直接去[官网](https://music.163.com/#/download)下载deb包，然后按照如下步骤进行安装：
* 安装debtap
    ```
    yay -S debtap
    ```
* 升级debtap
    ```
    sudo debtap -u
    ```
* 使用方法  
    安装时会提示输入包名，以及license。包名随意，license填GPL
    ```
    sudo debtap xxxx.deb
    ```

* 用pacman安装刚刚生成的xxxx.tar.xz文件
    ```
    sudo pacman -U xxxx.tar.xz
    ```

##### 安装金山wps

    yay -S wps-office

##### 安装微信
    yay -S wechat

##### 安装为知笔记
    yay -S wiznote

##### 安装vmware（暂时还有问题）

* 去[官网](https://my.vmware.com/en/web/vmware/info/slug/desktop_end_user_computing/vmware_workstation_pro/15_0#)下载linux版
* 安装
    ```
    chmod +x xxx.bundle
    echo /etc/init.d | sudo ./xxx.bundle
    ```

* 安装linux-headers  
  选择与你现在linux内核一致的版本安装
    ```
    sudo pacman -S linux-headers
    ```

* 设置vmware.service自启动
    ```
    sudo systemctl enable vmware.service
    sudo systemctl start vmware.service
    ```

### SSD配置
如果你的manjaro是安装在SSD上则可执行如下命令。

    sudo systemctl enable fstrim.timer
    sudo systemctl start fstrim.timer

### 引用及查阅的资料地址
* [manjaro下安装输入法 - awsome365 - 简书](https://www.jianshu.com/p/d7c8f29be182)
* [manjaro安装deb包 - 简书](https://www.jianshu.com/p/21bc10811b78)
* [manjaro踩坑记 - swolf的博客](https://mrswolf.github.io/zh-cn/2019/05/24/manjaro%E8%B8%A9%E5%9D%91%E8%AE%B0/)
* [VMware (简体中文) - ArchWiki](https://wiki.archlinux.org/index.php/VMware_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
* [Quick start guide | SpaceVim](https://spacevim.org/quick-start-guide/)