1.java android 的四大组件
  Activity
  Service
  BroadcastReceiver
  ContentProvider

2.架构
  android平台是由 操作系统(底层是建立在linux上)、中间件、用户界面、应用软件。组成
  android系统的组成
  应用程序层（各种应用、有系统级的应用（例如sms）和自定义开发的应用）
  应用程序框架（提供了大量的API供开发者使用）
  函数库（c/c++的库集合）开发者不能直接调用，需要通过应用程序框架的API调用
  Android运行时（java核心库集、Dalvik虚拟机）每个android程序都运行在单独的一个Dalvik虚android是由java编写的，所有有些人会吧Dalvik 虚拟机和java的jvm虚拟机搞混了但实际上Dalvik没有遵循jvm的规范，两者也不兼容，java的jvm是运行的java的字节码通常就是.class file 或jar包中的字节码 Dalvik没有办法直接从.class或jar file中读取字节码，它需要DX工具将应用程序中所有的.class file编译成.dex file Dalvik 运行.dex file。
  linux内核
  android 系统建立在linux 2.6之上。

  sdk的目录
  add-ons:   该目录下存放额外的附件软件，存放着附加库例如GoogleMaps。存放google api 的版本。
  platforms: 该目录存放不同版本的android版本（核心系统）。
  tools:     该目录下存放了大量的android开发、调试工具。
  SDK Manager该程序就是android sdk 和 AVD的管理器。
  doc:       该目录存放了android sdk 开发file和api等等
  platfrom-tools: 该目录存放了android平台相关的工具。
  sample:    该目录存放不同的android平台的示例程序
  为了在命令行可以直接使用android sdk 的各种工具建议tools 和 platfrom-tools加入path
老的安装流程
  sdk->eclipse->adt
  下载sdk安装 下载eclipse安装 下载adt然后在eclipse里面安装help->install new software->最后把sdk装到eclipse里面window->preferences->android->选择sdk的安装路径。
   eclipse download http://www.eclipse.org
   adt download     http://developer.android.com/sdk/eclipse-adt.html
   sdk              http://developer.android.com/sdk/index.html

Android 常用的开发工具的用法
  虚拟机 genymotion 再就是自带个的avd（有个interl加速）
  操作命令
  android list 显示所有的android版本以及创建安装的adt
  android list avd 显示所有安装的avd
  android list target 显示所有已经安装的android版本
  android create avd -n<avd name> -t<android version> -p<avd设备保存路径> -s<选择avd皮肤> 创建一个avd设备 （-n -t 是必选项，-p如果不写默认在 ANDROID_SDK_HOME的环境变量中存放 例如 android create avd -n leegang -t 6(6是android 2.3的代号)）
  android move avd 移动或重命名一个AVD设备
  android delete avd 删除一个AVD设备
  android update avd 升级一个AVD设备使之匹配新的SDK环境
  android create test-project 创建一个新的android测试项目
  android update test-project 更新一个已有的android测试项目
%ANDROID_SKD_HOME%/android目录
  hi.avd hi.ini hi avd 的基本信息和AVD设备。其中hi.avd 目录下有一个userdata.img file , 它是avd中用户数据镜像。还有一个sdcard.img,它是该avd所用的虚拟sd卡的镜像
android 模拟器（Emulator）
  android 模拟器就想一部运行在电脑上的虚拟手机
  emulator 启动方法 emulator -avd <AVD名称>
  例如：emulator -avd hi
  emulator -data 镜像file名称
  例如：emulator -data myfile作为镜像file来运行AVD设备
使用DDMS进行调试
  设备面板：DDMS窗口左上角的面板，该面板会列出所有运行的模拟器，并列出各个模拟器内部的所有进程信息。如果需要指定模拟器信息，应该在该面板中选中指定模拟器或进程。  信息输出面板：该面板位于DDMS下方，非常重要，相当于java的控制台
  线程跟踪面板：该面板可以用于查看指定进程内所有正在执行的状态。如果现实进程状态1点击thread 2在设备面板选中需要查看的进程。
  Heap内存跟踪面板：显示堆内存和分配和回收信息。点解heap在在设备面板选择需要查看进程。
  模拟器控制面板：该面板用于模拟器拨打电话，发送短信等，还可以虚拟设置模拟器的位置信息等。（打电话短信这个需要启动多个模拟器emulator后面有个号用这个号就行，不明白就看黑马的那套视频）
  file管理对话框：该对话框默认没有显示出来。可以通过工具条的Device->file Expleorer就可看到它的file系统
  如果eclipse安装了ADT查件默认会集成DDMS的，eclipse右上角有。或者单个打开windows->show view->other就可以。
  在就是搜索调试信息，过滤调试信息一般用tab过滤
Android Debug Bridge(ADB)用法
  adb可以实现电脑和虚拟机之间的拷贝，也可以切换到android系统使用linux命令，安装应用apk。在platform-tools里面的一个工具。
  adb的命令：
  adb devices 列出当前正在运行的模拟器。
  电脑与模拟器之间的file相互复制, 
  adb push d:/abc.txt /sdcard/ 将d:\abc.txt复制到/sdcard/下面去
  adb pull /sdcard/syz.txt d:/ 将sdcard下的内容复制到d:盘下面
  shell
    adb shell 启动android的shell 窗口
  安装、卸载apk程序
  打包APK的三个步骤
    1.通过DX工具对*.class file进行转换。转换后通常得到一个*.dex file
    2.通过AAPT工具打包所有的资源file,打包后通常得到*.ap_file
    3.通过apkbuild将12得到的*.dex *.ap_ file打包成apk包
  adb install -r -s 
    1.-r 表示重新安装apk
    2.-s 后面跟的是设备名称例如emulator-5554
  adb install aaa.apk -r -s emulator-5554
  卸载apk adb uninstall -k package
  1.-k 表示只删除应用程序，但保留该程序的数据和缓存目录。
  注意这里的package是data里面的那个package名字不是应用的名称。

DX编译工具
  dalvik运行的不是java的二进制file而是运行自己的.dex file, 因此我们需要使用DX将.class file 打包成.dex file
  DX工具的常见命令格式如下
  dx --dex [--dump-to=<file>] [--core-library] [<file>.class | <file>.{zip,jar,apk}|<dierctory>]
  上面的命令中[--dump-to<file>] 指定的是输出.dex  file的路径而--core-library是需要打包的.class .zip .jar file 或者目录
  dx --dex --dump-to=d:\aa.dex --core-library d:\aaa\bin
  将aaa目录下的所有二进制file都打包到aa.dex中

AAPT工具
  当开发android的时候应用可能会用到很多的资源，包括各种的图片音频这个时候我们需发布到一个apk包时就需要将资源打包.ap_
  相关的指令
    1.aapt l 列出资源压缩包内的内容。 
    2.aapt d 查看apk包内的指定内容。
    3.aapt p 打包生成资源压缩包。
    4.aapt r 从压缩包中删除指定file。
    5.aapt a 向压缩包中添加指定file
    6.aapt v 打印AAPT的版本。
打包指令
  aapt -A <附加资源的路径> -S <资源路径> -M <Android应用清单file> -I<额外添加的包> -F 目标file的路径。
  例如
  aapt -A assets -S res -M AndroidManifest.xml -I d:\...\...\platforms\android-9\atforms\android-9\android.jar -F bin\res.ap_
 上面的指令将当前目录下的assets子目录，res子目录, AndroidManifest.xml file都打包到 bin\res.ap_资源包中。

使用mksdcard管理虚拟的SD卡
  正如前面在android sdk 和 avd管理中见到，我们可以在创建avd设备时创建一个虚拟sd卡。实际上还可以使用mksdcard命令来创建单独的一个虚拟存储卡。
  mksdcard 命令如下
  mksdcard [-l label] <size> <file>
  上面的命令中<size> 指定虚拟SD卡的大小,<file>指定保存虚拟SD卡的file镜像。
  mksdcard 64M d:\avd\sdcard.img
  如果希望模拟器使用虚拟的SD卡，则需要在启动模拟器添加-sdcard <file>选项，其中<file>代表了虚拟SD卡的镜像
  emulator -avd aaa -sdcard d:\avd\sdcard.img
