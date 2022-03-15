### 需要的工具

1. git工具
    - 下载地址：https://git-scm.com/downloads
2. nodejs
    - nodejs 需要安装 12 or 14 or 16版本，我们安装14大版的最终版
    - 下载地址：https://nodejs.org/download/release/v14.19.0/
3. npm
    - 安装了nodejs会自带npm，但需要降级，不然操作项目时会出现奇怪问题。
4. angular
    - 安装12.1.2版本
3. 编辑器
    - vs code

### npm下的工具安装
1. npm降级
``` bash
npm install -g npm@6.14.13
```

2. angular安装12版本
``` bash
npm install -g @angular/cli@12.1.2
```

### 下载ihub项目
1. ihub分为主项目和子模块
``` bash
# 先下载主项目（最外层壳）
git clone ssh://git@git1.sh-fengze.com:2222/saas/fontend/iHub/ihub-app.git 
# 下载主项目下的子模块
git submodule init
git submodule update
```

2. 命令行里跳转目录到各个子模块的 source/framework文件夹下
3. 打开 openvpn
    - 有些依赖包在广州研发中心的内网服务器里，需要开vpn
4. 安装各模块的依赖包
``` bash
# ihub-app\framework\sources\framework>
npm run install:all
```
5. 启动项目
``` bash
npm run start
```