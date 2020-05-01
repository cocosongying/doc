# 环境准备

## npm & cnpm
升级 npm 到最新版本
```bash
npm i -g npm
```

安装 cnpm
```bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

## Node
安装node的版本管理工具 `n`
```bash
npm i -g n
```

安装最新长期支持的稳定版
```
n lts
```

## Nginx
```bash
apt update
apt install nginx
```

## Docker
```bash
apt-get update

apt install apt-transport-https ca-certificates software-properties-common curl

curl -fsSL http://mirrors.cloud.aliyuncs.com/docker-ce/linux/ubuntu/gpg | apt-key add -

add-apt-repository \
"deb [arch=amd64] http://mirrors.cloud.aliyuncs.com/docker-ce/linux/ubuntu \
$(lsb_release -cs) \
stable"

apt update

apt install docker-ce
```
## Docsify
用于快速搭建简约文档系统，官网地址 [https://docsify.js.org/](https://docsify.js.org/)
```bash
npm i docsify-cli -g
```

```bash
docsify init ./docs
```

```bash
docsify serve ./docs --port 3001
```

## Hexo

```bash
npm install -g hexo-cli
```

```
$ hexo init <folder>
$ cd <folder>
$ npm install

```