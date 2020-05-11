some tips for oscp
# WEB 边界突破

## PHP-reverse-shell
[php-reverse-shell-README.md](https://github.com/Jewel591/OSCP/blob/master/PHP-reverse-shell/README.md)

Referer：
- https://github.com/swisskyrepo/PayloadsAllTheThings

## ASP-reverse-shell
[asp-reverse-shell-README.md](https://github.com/Jewel591/OSCP/blob/master/ASP-reverse-shell/README.md)

# SYS 边界突破

# 后渗透
## Linux 提权
### 信息收集
- https://github.com/rebootuser/LinEnum
- https://github.com/AlessandroZ/BeRoot
- https://github.com/mzet-/linux-exploit-suggester
### SUID 提权
suid 辅助信息收集脚本：
[linux-pe-suid.sh](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/linux-pe-suid.sh)

原理:
```
#以下命令将尝试查找具有root权限的SUID的文件，不同系统适用于不同的命令，请逐个尝试
find / -perm -u=s -type f 2>/dev/null
find / -user root -perm -4000-print2>/dev/null
find / -user root -perm -4000-exec ls -ldb {} \;
```
已知的可用来提权的linux可行性的文件列表如下：

> Referer: https://www.hackingarticles.in/linux-privilege-escalation-using-suid-binaries/

- [nmap](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/nmap.md)
- [vim/vi](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/vim.md)
- [find](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/find.md)
- [bash](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/bash.md)
- [more/less](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/less-more.md)
- nano
- [cp/mv](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/cp-move.md)
- [python/perl/ruby/lua/etc](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/python-perl-ruby-lua-etc.md)
- [tcpdump(未验证)](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/tcpdump.md)
- [其他脚本文件](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/other-script-file.md)

## Windows 提权
### 提权方法
1. 不带引号的服务路径
2. 易受攻击的服务（>）
3. Windows AlwaysInstallElevated 策略
4. Unattended Installs
5. [内核提权](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/Kernel_Exploit.md)

## 提权工具
1. [Accesschk.exe](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/Accesschk.md)
2. [BeRoot](https://github.com/AlessandroZ/BeRoot/tree/master/Windows)
