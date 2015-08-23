---
layout: post
title:  "安装 Jekyll"
date:   2015-08-23 22:43:37
categories: article
---

# 安装 jekyll 

## 更换 gem source 为淘宝源

	gem sources --remove https://rubygems.org/
	gem sources -a https://ruby.taobao.org/
	gem sources -l

## 安装 jekyll

	gem install jekyll
	jekyll new think
	cd think
	jekyll serve

## 参考资料
1. [RubyGems淘宝镜像](http://ruby.taobao.org/ "RubyGems淘宝镜像")
2. [Jekyll](http://jekyllrb.com/ "Jekyll")
