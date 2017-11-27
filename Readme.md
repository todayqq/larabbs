# Larabbs

## 项目概述

LaraBBS，一个简洁的论坛应用


## 环境介绍

- Nginx 1.8+
- PHP 5.6+
- Mysql 5.7+
- Redis 3.0+
- Laravel 5.1.26 (LTS)

## 开发环境部署/安装

本项目代码使用 [Laravel Framework](http://laravel.com/) 进行开发,本地开发环境使用 [Laravel Homestead](http://laravel-china.org/docs/5.1/homestead) 进行快速部署.

下文将在假定读者已经安装好了 Homestead 的情况下进行说明. 如果您还未安装 Homestead, 可以参照 [Laravel Homestead Installation & Setup](http://laravel-china.org/docs/5.1/homestead#installation-and-setup) 进行安装配置.

### 基本安装

1. 克隆源代码

    将源代码克隆到 `larabbs` 文件夹下

    > git clone https://github.com/todayqq/larabbs.git

2. 配置本地的 Homestead 环境

    1). 编辑 Homestead.yaml 文件

    ```shell
    homestead edit
    ```

    2). 加入对应修改,如下所示:

    ```
    folders:
        - map: ~/Projects/larabbs/ # 你本地的项目目录地址
          to: /home/vagrant/larabbs

    sites:
        - map: larabbs.app
          to: /home/vagrant/larabbs/public

    databases:
        - larabbs
    ```

    3). 应用修改

    ```shell
    homestead provision
    ```

3. 安装依赖
    > composer install

4. 生成配置文件
    > cp .env.example .env

    你可以根据 .env 的文件内容进行相应修改,如数据库连接、缓存设置等内容

    ```
    APP_URL=http://larabbs.app
    ...
    DB_HOST=localhost
    DB_DATABASE=larabbs
    DB_USERNAME=homestead
    DB_PASSWORD=secret

    DOMAIN=.larabbs.app
    ```

5. 创建数据表及生成测试数据

    在 Homestead 的网站根目录下运行以下命令

    ```shell
    php artisan key:generate
    php artisan migrate --seed
    ```
6. 配置 hosts 文件
    > sudo vi /etc/hosts

    添加如下内容
    > 192.168.10.10 redbang.app

### 前端框架安装

1. 安装 node.js

    直接去官网 [https://nodejs.org/en/](https://nodejs.org/en/) 下载最新版本即可

2. 安装 Gulp

    ```shell
    npm install --global gulp
    ```

3. 安装 Laravel Elixir

    ```shell
    npm install
    ```

4. 安装 bower

    ```shell
    npm install --global bower
    ```

5. 运行 bower 下载前端组件包

    ```shell
    bower install
    ```

6. 直接 Gulp

    ```shell
    gulp
    ```

完成以上步骤后浏览器访问 http://larabbs.app/ 即可.

管理后台地址: http://larabbs.app/admin. 管理员账号密码如下:

至此, 安装完成 ^_^.



