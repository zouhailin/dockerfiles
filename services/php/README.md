## PHP 服务

Version based on official 7.4 alpine, runned by www-data

参考: https://hub.docker.com/r/nodeartio/php/dockerfile/

## 安装 redis 扩展

```
ENV REDIS_VERSION 5.1.1

RUN curl -L -o /tmp/redis.tar.gz https://github.com/phpredis/phpredis/archive/$REDIS_VERSION.tar.gz \
    && tar xfz /tmp/redis.tar.gz \
    && rm -r /tmp/redis.tar.gz \
    && mkdir -p /usr/src/php/ext \
    && mv phpredis-* /usr/src/php/ext/redis

RUN docker-php-ext-install redis    
```