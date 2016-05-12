title: NS2在Ubuntu下安装
date: 2016-05-05 20:45:31
tags: NS2
---

## 1. 下载ns-allinone-2.35压缩包

## 2. 安装依赖包

	sudo apt-get install binutils gcc g++ make glibc Xlibs-dev libx11-dev libxmu-dev libxmu-headers

## 3. 解压ns-allinone-2.35到指定目录，修改ns-2.35/linkstate/ls.h文件137行左右修改

	void eraseAll() { this->erase(baseMap::begin(),baseMap::end());}	

	
<!-- more -->

## 4. 运行./install

## 5. 在~/.zshrc中添加环境变量

	# ns2 environment path
	export PATH="$PATH:/opt/ns-allinone-2.35/bin:/opt/ns-allinone-2.35/tcl8.5.10/unix:/opt/ns-allinone-2.35/tk8.5.10/unix"
	export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/opt/ns-allinone-2.35/otcl-1.14:/opt/ns-allinone-2.35/lib"
	export TCL_LIBRARY="$TCL_LIBRARY:/opt/ns-allinone-2.35/tcl8.5.10/library"

