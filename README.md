# Aria2-Install-Windows
本项目适用于Windows32位或64位系统。
包含：`aria2.conf` 配置文件；`Aria2Control.vbs` Aria2简易控制台；以及Aria2相关文件。<br>
创建此项目目的在于存档记录部分已知问题的解决方式。

## Aria2简易控制台
`Aria2Control.vbs` 是本人利用VBS编写的简易窗体程序。实现对Aria2状态检测、启动、停止。

## 已知问题
* ### 缺少 `aria2.conf` 、 `aria2.log` 、 `aria2.session` 和程序启动文件。
> 原本的Aria2程序中是没有这些文件的，在Aria2 Windows版根目录下创建对应文件。<br>
> 新建TXT更名为 `aria2.log` 、 `aria2.session` 。<br>
> 配置文件可以使用本项目中的文件 `aria2.conf` 。<br>
> 启动文件可以使用本项目中的文件 `Aria2Control.vbs` 。<br>
* ### 点击“是”后报错，启动失败，提示缺少配置文件。
> 检查程序根目录下是否存在 `aria2.conf` 配置文件，并重新启动程序。
* ### 点击“否”后报错，停止失败。
> 再次尝试，若还是不行请在任务管理器中手动结束 `aria2c.exe` 。

## 相关扩展及注意事项
> ### 相关扩展
> * 修改下载路径：在 `aria2.conf` 配置文件中修改，重启程序后即可生效；
> * 配置开机启动：创建VBS控制台程序的快捷方式，放入```C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup```
> * VBS程序扩展：
>> ①启动命令：```CreateObject("WScript.Shell").Run ".\aria2c.exe --conf-path=aria2.conf",0```<br>
>> ②停止命令：```CreateObject("wscript.shell").Run "taskkill /f /im aria2c.exe",0```
> ### 注意事项
> * 切记在启动程序前确保根目录下已有配置文件，否则程序可能无法正常启动。
