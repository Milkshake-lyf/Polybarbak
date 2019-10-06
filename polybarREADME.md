# 这是我的polybar安装过程  
	安装字体  
	因为**已经安装了桌面环境和i3所以跳过**  
## 安装polybar  
	通过AUR仓库安装（个人使用yay）  
yay -S polybar-git  
	安装必要的**依赖**，Github上写有，也可在安装时候查看  
## 配置polybar
	在Github上clone了一个配置，然后复制文件到了~/.config/polybar/  
	然后看了官方的一个wiki配置启动的，这里简单写一下  
exec_always ~/.config/polybar/launch.sh  
同时注释i3 config 中的i3 bar  
# 注意
	polybar的config文件里的[bar/名字]需要和launch.sh里面的对应上  
	例如config里的是[bar/lyf]则launch.sh里的是polybar lyf  
# 同时也得注意一个显示器的问题（我的是VGA1）
monitor = ${env:MONITOR:VGA1}  
	这也是通常无法显示的原因  
	可以通过polybar -m 命令查看  
# polybar无法透明化
	如果你使用compton进行透明化，polybar可能会出现无法透明的情况。一方面可能与你的compton配置有关。另一方面，可能是你的polybar问题。  
	将[color]下的background修改为 background = #cc222222 ，从而实现透明化。
