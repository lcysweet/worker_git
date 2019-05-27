#### Genymotion模拟器

+ apk无法安装--Genymotion模拟器X86不支持ARM格式
  + 开发人员打的apk包--ARM,ARM-64,X86-64(没有支持x86)
  + 导致开发人员给的apk 包,Genytion模拟器不支持
  + 解决方案
    + 开发人员打包增加X86(包的大小将增加4-10M)-
      + android studio中，在gradle里的abiFilters内加入x86即可
      + 模拟器一般都是x86架构，所以如果工程有so库的，需要加载x86的so库；而真机一般都是arm架构的
    + Genymotion模拟器安装支持的格式的ARM.zip包
  + 遇到问题:安装arm后,可以成功安装apk包,但是点击运行发生崩溃闪退
    + ARM包版本不支持,错误
    + Genymotion模拟器手机版本--5.0版本:Genymotion_ARM_Translation_5.1_Lollipop.zip
    + Genymotion模拟器手机版本--6.0版本:ARM_Translation_Marshmallow.zip

```
安装ARM正确的方法:
1-Genymotion模拟器设置:
1,Genymotion--settings--ADB--Use custom Anrooid SDK tools--C:\MyTools\Genymotion\Genymotion\tools  
2-CMD命令:
2,C:\MyTools\Genymotion\Genymotion\tools---cmd
3-ADB命令安装:
1,adb push D:\android_studio_tools\Genymotion_ARM_Translation_5.1_Lollipop.zip /sdcard/Download/
2,adb shell flash-archive.sh /sdcard/download/Genymotion_ARM_Translation_5.1_Lollipop.zip

adb -s 设备id install app-release.apk--指定设备装apk
```

```
导入:.ova版本
Oracle VM VirtualBox--管理-导入虚拟电脑(ctrl+i)--选择路径.ora--下一步--勾选重新初始化所有网卡AMC地址--导入
```

