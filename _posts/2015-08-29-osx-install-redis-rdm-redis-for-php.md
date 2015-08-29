---
layout: post
title:  "OSX 安装 Redis、Rdm、PHP的扩展"
date:   2015-08-29 17:00:00
categories: article
---

# OSX 安装 Redis、Rdm、PHP的扩展

## 安装 Redis

	brew update 
	brew install redis

安装完成后提醒是否要登录时启动，如需要继续执行命令

	ln -sfv /usr/local/opt/redis/*.plist ~/Library/LaunchAgents
	launchctl load ~/Library/LaunchAgents/homebrew.mxcl.redis.plist

如果不需，那就需要时启动执行命令

	redis-server /usr/local/etc/redis.conf


## 安装 RedisDesktopManager(Rdm)

	brew install caskroom/cask/brew-cask 
	brew cask install rdm // 需要输入root密码

## 安装 PHP 相应版本的 Redis 扩展

	php -v 
	brew install php55-redis


## 参考资料

1. [RedisDesktopManager](http://redisdesktop.com/, 'RedisDesktopManager')
2. [RedisDesktopManager For GitHub](https://github.com/uglide/RedisDesktopManager/wiki/Install-and-Run, 'RedisDesktopManager For GitHub')
