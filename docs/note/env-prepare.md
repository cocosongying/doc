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

## Mysql
```bash
docker pull mysql:8.0

docker run -it -p 3306:3306 -v /mojipanda/docker/mysql/conf:/etc/mysql/conf.d -v /mojipanda/docker/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 --name mysql --restart=always -d mysql:8.0
```

## MongoDB
```bash
docker pull mongo:4.2

docker run -it -p 27017:27017 -v /mojipanda/docker/mongo/conf:/data/configdb -v /mojipanda/docker/mongo/data:/data/db --name mongo --restart=always -d mongo:4.2 --auth

docker exec -it mongo mongo admin

> db.createUser({ user:'root',pwd:'123456',roles:[ { role:'userAdminAnyDatabase', db: 'admin'}]});
```

## Redis
```bash
docker pull redis:6.0

docker run -it -p 6379:6379 -v /mojipanda/docker/redis/redis.conf:/etc/redis/redis.conf -v /mojipanda/docker/redis/data:/data --name redis --restart=always -d redis:6.0 redis-server --appendonly yes --requirepass "123456"
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

## Vue
```bash
npm install -g @vue/cli
```

```bash
vue create my-project
```