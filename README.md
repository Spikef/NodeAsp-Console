# NodeAsp Console

NodeAsp命令行调试工具，辅助基于NodeAsp框架进行网站开发。

![image](https://github.com/Spikef/NodeAsp-Console/raw/master/Snapshot.png)

## Environment

需要IIS7.5和.NET4才能运行，其它环境未测试。

## Usage

### 第一步：注册COM组件

以管理员权限打开CMD，使用REGASM命令注册component\Terminal.dll，其中REGASM位于C:\Windows\Microsoft.NET\Framework\v4.0.30319(具体位置与版本号有关)。

> 如果要更新，可以直接替换dll文件。或者使用/u反注册。

```
C:\Windows\Microsoft.NET\Framework\v4.0.30319\REGASM D:\component\Terminal.dll /codebase
```

### 第二步：修改注册表，解决 ASP 0177 : 8000ffff 错误

对于32位系统，找到如下注册表位置：
> HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\MAIN\FeatureControl\FEATURE_IGNORE_ZONES_INITIALIZATION_FAILURE_KB945701

对于64位系统，找到如下注册表位置：
> HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Internet Explorer\MAIN\FeatureControl\FEATURE_IGNORE_ZONES_INITIALIZATION_FAILURE_KB945701

选择或者新建项<code>FEATURE_IGNORE_ZONES_INITIALIZATION_FAILURE_KB945701</code>，然后新建DWORD值：

> 名称：w3wp.exe
> 值：1

### 第三步：启动Console

双击component\Console.exe，打开服务监视器。

## Commands

### cls

清空屏幕信息，不可恢复。

### about

显示作者信息。

### copylast

复制上次输出的内容。

### copyall

复制所有输出的内容。
