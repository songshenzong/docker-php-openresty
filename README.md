# Docker Image packaging for PHP & OpenResty

![docker hub](https://img.shields.io/docker/pulls/songshenzong/php-openresty.svg?style=flat-square)
![docker hub](https://img.shields.io/docker/stars/songshenzong/php-openresty.svg?style=flat-square)



##### 基于官方镜像 Based Official Image

```bash
openresty/openresty:alpine
```


##### 官网 Docker

```bash
docker pull songshenzong/php-openresty
```



##### 阿里云公网 Alibaba Cloud Internet

```bash
docker pull registry.cn-beijing.aliyuncs.com/songshenzong/php-openresty
```



##### 阿里云经典内网 Alibaba Cloud Intranet

```bash
docker pull registry-internal.cn-beijing.aliyuncs.com/songshenzong/php-openresty
```



##### 阿里云VPC网络 Alibaba Cloud VPC Network

```bash
docker pull registry-vpc.cn-beijing.aliyuncs.com/songshenzong/php-openresty
```


## Overview
This is a Dockerfile/image to build a container for nginx and php-fpm, with the ability to pull website code from git when the container is created, as well as allowing the container to push and pull changes to the code to and from git. The container also has the ability to update templated files with variables passed to docker in order to update your code and settings. There is support for lets encrypt SSL configurations, custom nginx configs, core nginx/PHP variable overrides for running preferences, X-Forwarded-For headers and UID mapping for local volume support.

If you have improvements or suggestions please open an issue or pull request on the GitHub project page.

### Version
| Docker Tag | GitHub Release | Nginx Version | PHP Version | Alpine Version |
|-----|-------|-----|--------|--------|
| latest | Master Branch |1.13.6.1 | 7.2.2 | 3.6 |

For other tags please see: [Version](https://github.com/songshenzong/php-openresty/blob/master/docs/versioning.md)

### Links
- [https://github.com/songshenzong/php-openresty](https://github.com/songshenzong/php-openresty)
- [https://registry.hub.docker.com/u/songshenzong/php-openresty](https://registry.hub.docker.com/u/songshenzong/php-openresty)

## Quick Start
To pull from docker hub:
```
docker pull songshenzong/php-openresty:latest
```
### Running
To simply run the container:
```
sudo docker run -d songshenzong/php-openresty
```
To dynamically pull code from git when starting:
```
docker run -d -e 'GIT_EMAIL=email_address' -e 'GIT_NAME=full_name' -e 'GIT_USERNAME=git_username' -e 'GIT_REPO=github.com/project' -e 'GIT_PERSONAL_TOKEN=<long_token_string_here>' songshenzong/php-openresty:latest
```

You can then browse to ```http://<DOCKER_HOST>``` to view the default install files. To find your ```DOCKER_HOST``` use the ```docker inspect``` to get the IP address (normally 172.17.0.2)

For more detailed examples and explanations please refer to the documentation.
## Documentation

- [Building from source](https://github.com/songshenzong/php-openresty/blob/master/docs/building.md)
- [Version](https://github.com/songshenzong/php-openresty/blob/master/docs/versioning.md)
- [Config Flags](https://github.com/songshenzong/php-openresty/blob/master/docs/config_flags.md)
- [Git Auth](https://github.com/songshenzong/php-openresty/blob/master/docs/git_auth.md)
 - [Personal Access token](https://github.com/songshenzong/php-openresty/blob/master/docs/git_auth.md#personal-access-token)
 - [SSH Keys](https://github.com/songshenzong/php-openresty/blob/master/docs/git_auth.md#ssh-keys)
- [Git Commands](https://github.com/songshenzong/php-openresty/blob/master/docs/git_commands.md)
 - [Push](https://github.com/songshenzong/php-openresty/blob/master/docs/git_commands.md#push-code-to-git)
 - [Pull](https://github.com/songshenzong/php-openresty/blob/master/docs/git_commands.md#pull-code-from-git-refresh)
- [Repository layout / webroot](https://github.com/songshenzong/php-openresty/blob/master/docs/repo_layout.md)
 - [webroot](https://github.com/songshenzong/php-openresty/blob/master/docs/repo_layout.md#src--webroot)
- [User / Group Identifiers](https://github.com/songshenzong/php-openresty/blob/master/docs/UID_GID_Mapping.md)
- [Custom Nginx Config files](https://github.com/songshenzong/php-openresty/blob/master/docs/nginx_configs.md)
 - [REAL IP / X-Forwarded-For Headers](https://github.com/songshenzong/php-openresty/blob/master/docs/nginx_configs.md#real-ip--x-forwarded-for-headers)
- [Scripting and Templating](https://github.com/songshenzong/php-openresty/blob/master/docs/scripting_templating.md)
 - [Environment Variables](https://github.com/songshenzong/php-openresty/blob/master/docs/scripting_templating.md#using-environment-variables--templating)
- [Lets Encrypt Support](https://github.com/songshenzong/php-openresty/blob/master/docs/lets_encrypt.md)
 - [Setup](https://github.com/songshenzong/php-openresty/blob/master/docs/lets_encrypt.md#setup)
 - [Renewal](https://github.com/songshenzong/php-openresty/blob/master/docs/lets_encrypt.md#renewal)
- [PHP Modules](https://github.com/songshenzong/php-openresty/blob/master/docs/php_modules.md)
- [Xdebug](https://github.com/songshenzong/php-openresty/blob/master/docs/xdebug.md)
- [Logging and Errors](https://github.com/songshenzong/php-openresty/blob/master/docs/logs.md)

## Guides
- [Running in Kubernetes](https://github.com/songshenzong/php-openresty/blob/master/docs/guides/kubernetes.md)
- [Using Docker Compose](https://github.com/songshenzong/php-openresty/blob/master/docs/guides/docker_compose.md)
