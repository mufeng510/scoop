# Scoop

## 改动

-   安装同名包时首选`main`仓库里的
-   添加桶时使用浅克隆加速
-   集成`github`镜像，能在墙内更快的下载来自`github`的文件。为了降低`github`镜像的负担，仅在墙内生效，判断依据能否访问`v2ray.com/robots.txt`
-   调整了`aria2`的默认参数，以最大化下载速度
-   默认启用`use_sqlite_cache`配置
-   安装脚本改自[`ScoopInstaller/Install`](https://github.com/ScoopInstaller/Install/blob/master/install.ps1)。安装时附带了`apps`桶[`kkzzhizhou/scoop-apps`](https://github.com/kkzzhizhou/scoop-apps)，聚合了绝大部分 scoop 桶，开箱即用

## 安装

普通用户执行

```powershell
Set-ExecutionPolicy rem -s c;iwr -useb https://mirror.ghproxy.com/https://raw.githubusercontent.com/mufeng510/scoop/master/install.ps1 | iex
```

管理员执行

```powershell
Set-ExecutionPolicy rem -s c;iwr -useb https://mirror.ghproxy.com/https://raw.githubusercontent.com/mufeng510/scoop/master/install.ps1 -outfile 'install.ps1';.\install.ps1 -RunAsAdmin;rm .\install.ps1
```

## 建议安装

```powershell
scoop install sudo scoop-search
```

- sudo 以管理员权限运行后续命令
- [scoop-search](https://github.com/shilangyu/scoop-search) 更快的搜索软件

## 一行代码更新软件及删除旧版及缓存

```powershell
sudo scoop update | scoop update * -s | scoop cleanup * | scoop cache rm *
```

## 设置代理

```powershell
#在国内的环境下，无法避免会有部分网址无法链接需要代理
scoop config proxy 你的代理地址

#移除代理
scoop config rm proxy
```

## 更多用法

```powershell
scoop help
```

## 设置

```powershell
scoop help config
```
