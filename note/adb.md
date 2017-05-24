### adb(/home/huanglei/Android/Sdk/platform-tools/adb)
    
- 基本语法
    - adb [-d|-e|-s <serialNumber>] <command>
- 查找设备
    - adb devices
- 启动/停止
    - adb start-server
    - adb kill-server
- 查看 adb 版本
    - adb version
- 指定 adb server 的网络端口
    - adb -P <port> start-server 默认端口为 5037。
- 通过 IP 地址连接设备
    - adb connect <device-ip-address>
- 断开无线连接
    - adb disconnect <device-ip-address>
- 安装 APK
    - adb install [-lrtsdg] <path_to_apk>

      |参数 |	含义|
      |------------ | ------------ |
      |-l	|将应用安装到保护目录 /mnt/asec|
      |-r	|允许覆盖安装|
      |-t	|允许安装 AndroidManifest.xml 里 application 指定 android:testOnly="true" 的应用|
      |-s	|将应用安装到 sdcard|
      |-d	|允许降级覆盖安装|
      |-g	|授予所有运行时权限|
- 卸载应用
    - adb uninstall [-k] <packagename>
- 复制设备里的文件到电脑
    - adb pull <设备里的文件路径> [电脑上的目录] 
- 复制电脑里的文件到设备
    - adb push <电脑上的文件路径> <设备里的目录>
- 同步拷贝的文件
    - adb sync [DIR] 
- 查看日志
    - [adb] logcat [<option>] ... [<filter-spec>] ...
    Android 的日志分为如下几个优先级（priority）：

        |type|desc|
        |---|---|
        |V|Verbose（最低，输出得最多）|
        |D|Debug|
        |I|Info||
        |W|Warning|
        |E|Error|
        |F|Fatal|
        |S|Silent（最高，啥也不输出）|
- 屏幕截图
    - adb exec-out screencap -p > sc.png
- 重启手机
    - adb reboot
- 重启到 Fastboot 模式
    - adb reboot bootloader
