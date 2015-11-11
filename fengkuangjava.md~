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
 
使用eclipse创建android项目大致分为三个步骤
  1.创建android项目
  2.在xml中编写应用的界面
  3.在java代码中编写业务逻辑
  ==
  1=> eclipse->file other or 工具条上的建立android项目
  2=> 项目的res目录->layout->....xml 这个file在编辑的时候可以所见即所得。
  3=> src->project.java
  4=> R file是android的一个资源file里面定义了所有res资源中的引用在java代码通过R
file里面定义的内容来引用资源
  布局xml的清单
  LinearLayout 代表的是线性布局
  组件TextView 代表的是一个输入框
  Button普通的类  这里为什大写因为每一个组件都是一个java类
  android:id 该属性指定了该控件的唯一标识，在java程序中通过findViewById("id")来获取当然这里应该使用的是 R资源这个是自动的当你创建一个ID那么就会自动写入到这个file引用的时候 findViewById(R.id....)。
  android:layout_width,android:layout_height这两个属性不关什么组件都应该有否则组件是不显示的。
  android:layout_width android:layout:height 有两个值 fill_parent则说明和父容器的宽度相同 wrap_content说明根据组件的内容决定，当然这里也可设置定值。
  为什么使用xml编写UI囊其实是为了降低o he性，java代码就负责业务逻辑，xml就来负责UI的实现可以把这个XML当做HTML来书写只不过语法不同
  项目src下面的那个入口file编写
  setContentView(R.layout.main) 设置布局file可以算是入口
  Button bt = (Button) findViewById(R.id.aa);获取button按钮，这里需要强制转一下否则拿不到。
  bt.setOnClickListener(new OnClickListener(){
      public void onClick(View e){
          final TextView tx = (TextView) findViewById(R.id.text);
	  tx.setText("string"+java.util.Date());
      }
  })
  1.布局该Activity使用main.xml
  2.获取按钮的id
  3.监听事件。
  findViewById()完全可以当作JS的getElementById
  
通过ADT 运行android应用
  1.通过Android SDK 和 AVD管理器 或直接使用emulator来运行avd设备
  2.邮件项目run as去在模拟器上安装项目。

Android应用结构分系
  抛开IDE来建立一个项目
  手动创建一个android的命令。
  android create project -n HelloWorld -t 6 -p HelloWorld -k com.theadventus.helloworld -a HelloWorld
  上面的命令中，-n指定项目的名称，-t指定android平台，-p指定项目存放路径，-k指定项目包名，-a指定Activity名称。
  目录结构的汾西
  HelloWorld
    |-res
         |-values
         |-layout
         |-drawable-ldpi、drawable-mdpi、drawable-hdpi
    |-src
         |-存放java源file
    |-AndroidManifes.xml
  res src AndroidManifest.xml 这三个是必选的其他的是可选的。
  res目录：存放android的各种资源file，比如layout布局界面，values目录下面存放各种xml格式的资源file,例如字符串file string.xml 存放字符串资源 color.xml存放颜色 尺寸资源 dimens.xml drawable-ldpi drawable-mdpi drawable-hdpi 这三个目录分别存放小、中、大三种图片file.
  src目录：只是一个普通的、保存java资源file.
  AndroidManifest.xml file是Android项目的系统清单file. 它用于控制android的名称，图标，访问权限等整体属性。
  除此之外，build.xml这个是android为该项目提供的一个Ant生成file,通过该生成file，开发者可以通过ant来生成、安装Android 项目。 安装document在目录下有。
  ant相关的命令说明 进入到项目目录
  1.clean:清除项目生成的内容--也就是回复打包前的样子。
  2.debug 打包一个调试用的apk
  3.release 打包一个发布到android 应用的apk
  4.install 将生成的调试apk安装到模拟器(这个建议使用 ant installd 是安装debug apk 到模拟器，因为安装release的没有证书)
  5.help 帮助
  6.uninstall 从模拟器卸载
  download path ant.apache.org/bindownload.cgi
  注意ant 需要两个环境变量
    1.JAVA_HOME这个是JDK所在的路径 
    2 ANT_HOME 该环境变量指向ant的安装路径。就是下面有bin docs etc lib的那个目录
   可以在命令行这么用%ANT_HOME%/bin/ant.bat 也可以都加入环境变量。
   在ant debug 或者 ant installd 编译后就会产生 bin 和 gen目录
   bin:该目录用于存放，java的二进制file,资源打包file .ap_ 以及dalvik 虚拟机的可执行file .dex file
    gen:该目录用于保存android自动生成的一个R.java 清单。这个file不在说明就是资源的引用。
  自动生成的R.java
  R.java类是由aapt工具根据资源file来动态生成的，因此我们可以把R.java理解为字典。aapt 生成的R.java主要有两条规则
  1.每个资源对应着R类的一个内部类，例如布局的layout，字符串的string，以及id等等。
  2.每个具体的资源对应着一个内部的public static final int 类型的Field 例如ID的
  在布局中使用了id 因此在R.id类就包括了这两个Field R.id.定义ID名 由于drawable-xxx 包含了icon.png 因此也就有了R.drawable.图片名字

res目录说明
  Android 应用的res目录是一个特殊的目录，该目录里存放了全部的资源，包括图片，字符串，颜色，尺寸等等
  Android 按照约定，将不同的资源放到不同的的目录，这样可以方便让AAPT工具来扫描这些资源，并为它们生成对应的资源清单：R.java
  在xml中使用资源 @string/app_name
  有一种例外，@+id/aaa 这个是定义一个ID 而 @id/aaa这个才是引用一个ID

Android 应用的全局清单file AndroidManifest.xml 描述了应用的名称，图表，以及包含的组件等。
  通常包括如下：
  1.应用的包名，作为应用的唯一表示
  2.应用所包含的组件，如Activity Service BroadcastReceiver Content Provider
  3.应用程序所兼容的最低版本。
  4.应用程序使用系统所需要的权限声明。
  5.其他程序访问该程序所需要的权限声明。
  package 指定包名
  android:versionCode=1给机器看的判断是否需要更新1-n
  android:versionName=1.0给我们自己看的版本
  //这个有两组 application是设置手机列表里面的，而activity才是设置桌面的
  android:label="@string/app_name" 定义应用的名称
  android:icon="@drawable/icon" 定义图标
  <intent-filter>
      设置该Activeity是入口
      <action android:name="android.intent.action.MAIN" />
      指定加载应用时运行该Activity
      <category android:name="android.intent.category.LAUNCHER" />
  </intent-filter>
  这里必须有否则没有入口
  android:label="@string/app_name" 引用的是/res/value/strings.xml
  android:icon="@drawable/icon" /res/drawable-l/m/hdpi的图标

应用程序的权限说明
  一个android的应用可能需要权限才能去调用android的系统功能，例如电话，短信。
  一个android应用也可能被其他应用，因此它也需要声明调用自身所需要的权限。
  声明应该有的自身权限，可以通过，工具直接添加也可直接写code
  1.声明该应用即有打电话的权限
  <uses-permission android:name="android.permission.CALL_PHONE">
  2.声明调用该应用程序自身需要的权限（别人调用你的）
  
Android应用的基本组件介绍
  Android应用通常是由一个或多个基本组件组成的，前面我们看到的android应用中最常用的组件就是Activity。 事实上android应用还包括Service BroadcastReceiver ContentProvider等组件。
Activity 和 View
  Activity 是Android应用中负责与用户交互的组件。 可以把它想象成swing编程中的JFrame控件。不过区别在于JFrame本身可以设置布局管理器，不断向JFrame中添加组件，但Activity只能通过setContentView(View)来显示指定组件。
  View组件是所有UI控件、容器控件的基类 View组件就是Android应用中用户实实在在看到的部分。但View组件需要放到容器中，或者使用Activity将它显示出来。如果需要通过某个Activity把指定的View显示出来，调用Activity的setContentView()即可。
  setContentView() 方法可以接收一个View对象作为参数。
  LinearLayout layout = new LineLayout(this);
  super.setContentView(layout);
  LinearLayout 是 ViewGroup 的子类，ViewGroup 又是 View的子类，接着调用Activity的setContentView(layout)把这个布局管理器显示出来。
  setContentView()方法可以接受一个布局管理器的ID作为参数
  setContentView(R.layout.main) 设置该Activity显示main.xml 定义的view
  ----------------------------------------------
  实际上Activity是window的容器，activity有一个getWindow()的方法，返回该Activity所包含的窗口。如果Activity的setContentView()不设置显示内容就是个空的窗口。
  Activity 为Android应用提供了可视化用户界面，如果该Android应用需要多个用户界面，那么这个Android应用将包含多个Activity，多个Activity组成Activity栈，当前活动的Activity位于栈定。
  Activity包含了一个setTheme(int resid) 方法来设置其窗口的风格，例如我们希望窗口不显示标题、一对话框的方式来显示，都可以通过该方法实现。

  ----------------------------------------------  
Service
  Service与Activity低位是并列的，它是运行在后台的没有用户界面，它是运行提供后台服务或监听其它组件运行状态的，它的声明周期是独立的。

BroadcastReceiver 是Android 代表广播消息接收器。
  相当于时间源，只不过事件源是对象，BroadcastReceiver监听的事件源是Android应用中的其它组件。
  使用BroadcastReceiver组件接收广播比较简单，开发者只要实现BroadcastReceiver子类，并重写onReceiver(Context context, Intent intent)方法即可。当其它组件通过sendBroadcast() sendStickyBroadcast() 或者 sendOrderBroadcast()方法发送广播消息时，如果该BrocastReceiver也对该消息感兴趣（通过IntentFilter配置），BroadcastReceiver的onReceiver(Context contex, Intent intent) 方法就会被触发。
  实现完了还需要注册 注册可以通过在java代码中使用Context.regisReceiver()
  或者在AndroidManifest.xml 中使用<receiver.../>完成注册

ContentProvider
  对于Android的应用程序来讲，他们每个应用都有自己的Dalvik的虚拟机，且运行在自己的虚拟机上，如果需要横跨多个应用进行数据传递那么需要使用ContentProvider,需要实现如下抽象方法。
  insert(Uri,ContentValues) 向ContentProvider 插入数据。
  delete(Uri,ContentValues) 删除ContentProvider中指定的数据。
  update(Uri,ContentValues,String, String[])更新ContentProvider中的数据。
  query(Uri,String[],String,String[],String)查询
通常与ContentProvider结合使用的是ContentResolve，一个应用程序使用ContentProvider暴漏自己的数据，而另一个应用通过ContentResolver来访问数据。

Intent 和 IntentFilter
  Intent 是Activity Service BroadcastReceiver 三者组件之间的通信载体。
  1.当启动一个Activity 可以调用Context的startActivity(Intent intent)方法，该方法中的Intent参数封装需要启动的目录Activity的信息。
  2.当启动一个Service Content startService(Intent intent) 方法或bindService(Intent service, ServiceConnection conn, int flags)方法，这两个中的intent封装了启动Service的信息
  3.BroadcastReceiver Context sendBroadcast send..... 封装了触发的目标BroadcastTrceiver的信息。
  显示Intent:显示Intent 明确指定需要启动或触发的组件的名称。
  隐式Intent:隐式Intent 只是指定需要启动或者触发的组件应满足怎样的条件。
  显示的系统直接找到指定的目标组件，启动它。
  隐式的android系统需要对该Intent进行解系，然后汾西出条件，在去系统中查找匹配的组件，最后触发它们。
  那么如何判断是隐式和显式的需要用到IntentFilter

Android 的视图组件与容器组件
  Android绝大部分UI组件都放在android.widest 包及其子包 android.view包及其子包。
Anddroid 应用所有UI都继承了view类，View组件非常类似于swing编程的jpanel它代表一个空白的区域。
  api docs index.html open then click Develop->Referece 即可
  Guides 和 Referenc  两个标签的内容是Android的document

Android UI由 xml布局或者使用java程序代码中通过调用方法进行控制。
  ViewGroup是一个抽象类，因此实际中通常使用ViewGroup的子类作为容器。
  ViewGroup容器控制其子组件分别依赖于ViewGroup.LayoutParams ViewGroup.MarginLayoutParams两个内部类。这个两个内部类中提供了一些XML属性，ViewGroup 容器中的子组件可以指定这些XML属性
    ViewGroup.LayoutParams
      1.android:layout_height
      2.android:layout_width	
      三个值fill_path和父辈一样。
      match_parent等同上面那个。
      wrap_content这个和内容一样。
   ViewGroup.MarginLayoutParams
      1.android:layout_marginButton
                             Left
                             Right
                             Top
   其它的后续继续介绍

使用XML布局控制UI
  1.setContentView(R.layout.资源名)切换使用哪个Activity 在res/layout建立然后引用R file
  2.UI布局如果指定ID android:id 可以在java代码中使用findViewById(R.id....)获得组件的控制就可以通过方法设置其UI，或者设置监听等

在代码中控制UI界面
  虽然Android推荐XML的UI布局，但是完全可以使用代码开发就想swing一样抛开XML，完全由java代码中控制UI界面。通过NEW的方式创建出来，然后在以和是的方式组装在一起。
  LinearLayout layout = new LinearLayout(this);
  super.setContentView(layout);
  layout.setOrientation(LinearLayout.VERTICAL);
  TextView show = new TextView(this);
  Button bn = new Button(this);
  bn.setText("aaaa");
  bn.setLayoutParams(new ViewGroup.LayoutParams(ViewGroup.LayoutParams.WRAP_CONTENT,ViewGroup.LayoutParams.WRAP_CONTENT));
  layout.addView(show);
  layout.addView(bn);

使用xml布局file和java代码混合控制代码
  将那些经常变化的放在java代码中，相反较为简单不经常变化的写在xml中。
  int []image = image[]{R.drawable.java};
  super.setContentView(R.layout.xxx);
  LinearLayout ly = (LinearLayout)findViewById(R.id...);
  ImageView iv = new ImageView(this);
  ImageView.setImageResource(images[0]);//this is images path
  ly.addView(ImageView);
  image.setOnClickListener(new OnClickListener(){
    public void onClick(View v){
	ImageView.setImageResource(images[1]);
    }

  })

开发自定义View
  前面提到过View 类似于Swing编程中JPanel,它只是一个矩形的空白区域，Viiew组件没有任何内容，对于Android应用的其它UI组件来说，它们都继承了View组件，然后在View组件提供的空白区域上绘制外观。
  如果用户需要自定义UI组件需要继承View类，然后重写一个或多个方法
    可以被重写的方法如下：
      1.构造器，重写构造器是指定View的最基本方式，当java代码创建一个View实例，或根据XML布局加载并构建界面将需要调用该构造器。
      2.onFinishInflate() 这是一个回调方法,当引用从XML布局加载该组件并利用它来构建界面后，该方法就会被回调。
      3.onMeasure(int, int) 调用该方法来检测View组件及它所包含的所有子组件的大小。
      4.onLayout(boolean,int,int,int,int) 当该组件需要分配其子组件的位置，大小时，该方法就会被回调。
      5.onSizeChanged(int,int,int,int) 当该组件的大小被改变这个方法就会被调用。
      6.onDraw(Canvas) 当该组件将要绘制它的内容时回调该方法进行绘制。
      7.onKeyDown(int,KeyEvent)
      8.onKeyUp(int,KeyEvent)
      9.onTrackballEvent(MotionEvent)当发生轨迹球事件时触发该方法。
      10.onTouchEvent(MontionEvent)触发触屏事件
      11.onWindowFocusChanged(boolean)当该组件得到失去焦点触发。
      12.onAttachedToWindow() 当把该组件放入到某个窗口触发。
      13.onDelachedFromWindow() 当把该组件从某个窗口分离触发。
      14.onWindowVisibilityChanged(int) 当包含该组件的窗口的可见性发生改变触发该方法。
  上面的不是需要全部重写只需要部分重写。

public class MyDraw extends View{
   public float x = 10;
   public float y = 10;
   public MyDraw(Context Context){
	super(Context);
   }
   public void onDraw(Canvas canvas){
	super.onDraw(canvas);
        Point p = new Point();
        p.setColor(Color.RED);
        canvas.drawCircle(x,y,p);
   }
}

public class CustomView extends Activity
{
    public void onCreate(Bundle b){
        super.onCreate(b);
        setContentView(R.layout.main);
        LinearLayout ly = (LinearLayout)findViewById(R.id...);
        MyDraw md = new MyDraw(this);
        md.setMinimumWidth(200);
        md.setMinimumHeight(200);
        md.setOnTouchListener(new OnTouchListener(){
           public boolean onTouch(View ag0, MotionEvent event){
		md.x = event.getX();
                md.y = event.getY();
                md.invalidate();//重绘
                return true;
           }

        })
        ly.addView(md);
    }

}

布局管理
  每个布局组件都是UI组件它们是ViewGroup的子类。
  类图： View
          |
       ViewGroup
          |
 AbsoluteLayout FrameLayout LinearLayout RelativeLayout TableLayout

线性布局 LinearLayout
 1.组件横向布局 一个挨着一个的排列如果超出手机屏幕范围也不会换行。
 2.组件纵向布局

android:gravity：

这个是针对控件里的元素来说的，用来控制元素在该控件里的显示位置。例如，在一个Button按钮控件中设置如下两个属性，

android:gravity="left"和android:text="提交"，这时Button上的文字“提交”将会位于Button的左部。



android:layout_gravity：

这个是针对控件本身而言，用来控制该控件在包含该控件的父控件中的位置。同样，当我们在Button按钮控件中设置android:layout_gravity="left"属性时，表示该Button按钮将位于界面的左部。
 
 相关用法。
 这两个属性可选的值有：top、bottom、left、right、center_vertical、fill_vertical、center_horizontal、fill_horizontal、center、fill、clip_vertical。
一个属性可以包含多个值，需用“|”分开。其含义如下：
top	将对象放在其容器的顶部，不改变其大小.
bottom	将对象放在其容器的底部，不改变其大小.
left	将对象放在其容器的左侧，不改变其大小.
right	将对象放在其容器的右侧，不改变其大小.
center_vertical	将对象纵向居中，不改变其大小. 
垂直对齐方式：垂直方向上居中对齐。
fill_vertical	必要的时候增加对象的纵向大小，以完全充满其容器. 
垂直方向填充
center_horizontal	将对象横向居中，不改变其大小. 
水平对齐方式：水平方向上居中对齐
fill_horizontal	必要的时候增加对象的横向大小，以完全充满其容器. 
水平方向填充
center	将对象横纵居中，不改变其大小.
fill	必要的时候增加对象的横纵向大小，以完全充满其容器.
clip_vertical	
附加选项，用于按照容器的边来剪切对象的顶部和/或底部的内容. 剪切基于其纵向对齐设置：顶部对齐时，剪切底部；底部对齐时剪切顶部；除此之外剪切顶部和底部.
垂直方向裁剪
clip_horizontal	
附加选项，用于按照容器的边来剪切对象的左侧和/或右侧的内容. 剪切基于其横向对齐设置：左侧对齐时，剪切右侧；右侧对齐时剪切左侧；除此之外剪切左侧和右侧.
水平方向裁剪

我们主要来看看center_vertical和center_horizontal两个属性值，center_vertical是指将对象在垂直方向上居中对齐，即在从上到下的方向上选择中间的位置放好；center_horizontal是指将对象水平方向上居中对齐，即在从左到右的方向上选择中间的位置放好。



3.特殊情况
当我们采用LinearLayout布局时，有以下特殊情况需要我们注意：
(1)当 android:orientation="vertical"  时， android:layout_gravity只有水平方向的设置才起作用，垂直方向的设置不起作用。即：left，right，center_horizontal 是生效的。
(2)当 android:orientation="horizontal" 时， android:layout_gravity只有垂直方向的设置才起作用，水平方向的设置不起作用。即：top，bottom，center_vertical 是生效的。


android:gravity setGravity(int) 子组件的位置。
android:orientation setOrientation(int) 子组件排列方式

多个值用|分割 竖线前后不能出现空格。


表格布局
  表格布局由TableLayout所代表。
  向TableLaout 添加每一个TableRow就是一行，向每一个TableRow添加组件就是一列，如果直接向TableLayout添加组件那么这个组件就占一行。
  表格管理器中，可以为单元格设置三种行为方式。
  1.Shrinkable如果设置了那么该列所有的单元格宽度可以被收缩，保证整个表格适应父辈宽度。
  2.Stretchable如果设置了那么该列所有的单元格宽度可以被拉伸，保证组件能完全填满表格的剩余空间。
  3.Collapsed如果设置了那么该列所有的单元格会被隐藏
TableLayout 继承了LinearLayout因为他完全可以用LinearLayout的全部属性。
  android:collapseColumns setColumnCollapsed(int,boolean) 设置需要被隐藏的列的列号，多个列号之间用逗号分隔
  android:shrinkColumns setShrinkAllColumns(boolean)设置允许被收缩列的列号，多个列号用逗号分隔。
  android:stretchColumns setStretchAllColumns(boolean)设置允许被拉伸的列的列号，多个列号之间用逗号分隔。
  举例说明
  <TableLayout 
    android:shrinkColumns="1"
    android:stretchColumns="2"
    android:collapseColumns="3,4"
  >
  </TableLayout>
  列从0开始
  指定第二列可以收缩，第三列可以拉伸。
  指定四五列被隐藏。
  
帧布局 FrameLayout
  FrameLayout直接继承了ViewGroup
  帧布局容器为每个加入其中的组件创建一个空白的区域称为一帧，所有每个子组件占据一帧，这些帧都会根据gravity属性自动对齐。
  android:foreground setForeground(Drawable) 设置该帧布局容器的前景图像
  android:foregroundGravity setForegroundGravity(int) 定义绘制前景图像的gravity属性。
  这个如果发生覆盖没有办法调整层级关系的，也就说后出来的在最上面。
  它是支持android:orientation="vertical"的
  68页有个实例
  时间轮训
  new Timer().schedule(new TimerTask(){
      @Override
      public void run(){
         //code
      }

  },0,100) //每100毫秒执行一次


相对布局RelativeLayout 相对布局总是相对父辈组件，兄弟组件所以被称为相对布局。
  如果A组件的位置是由B确定的那么需要先定义B在定义A
  RelativeLayout所示的两个xml属性。
  android:gravity setGravity(int) 设置该布局容器各个子组件的对齐方式。
  android:ignoreGravity setIgnoreGravity(int) 设置哪个组件不受到gravity组件的影响。
  为了控制分布，RelativeLayout提供了一个内部类：RelativeLayout.LayoutParams
  RelativeLayout.LayoutParams 里只能设置为boolean值的属性
  android:layout_centerHorizontal 该子组件是否位于布局容器的水平居中的位置。          layout_centerVertical   ...............................垂直居中位置。
          layout_centerInParent   ...............................垂直居中位置
                 alignParentButtom 底对齐
                 alignParentLeft   左对齐
                 alignParentRight  右对齐
                 alignParentTop    顶对齐


RelativeLayout.LayoutParams 里属性值为其它UI组件ID的XML。
  android:layout_toRightOf  位于给出ID组件的右侧
                 toLeftOf                   左侧
                 above                      上方
                 below                      下方
                 alignTop,Bottom,Left,Right 上下左右
这个注意对齐会拉伸组件
这个倒时测试下看看会不会和线性布局一样如果ori属性为横向横向居中的属性不好用。
除此之外RelativeLayout.LayoutParams 继承了android.view.ViewGroup.MarginLayoutParams 因此他有一些MarginLayoutParams的XML属性。

梅花布局就是中间有个其它的相对于它布局。
清单CODE 71
XML的引用资源
  1.ID是@id/...
  2.图片是@drawable/....图片名字


绝对布局absoluteLayout这个没什么价值没法办适应不同适配器。
  组件的属性layout_x layout_y控制这个组件的位置
  code 72


!!!!!android 支持的尺寸!!!!!!!!!
px 像素：每个PX对应屏幕的一个点
dip 或这是 dp 一种基于屏幕密度的抽象单位。在每英寸160点的显示器上1dip = 1px 随着密度的改变dip与px发生改变
sp 主要处理字体大小可以根绝用户的字体大小首选项进行缩放。
in 英寸长度单位
mm 毫米长队单位
pt 磅 长度单位1/72 英寸

基本界面组件
  1.问本框TextView 与 编辑框 EditText 的功能和用法。
  TextView 继承了View 它也是EditText和Button这两个组件的父类，它相当于Swing中的JLabel但是它比JLabel更加强大。 
  从功能上讲TextView就是一个wen本编辑器，只是android关闭了它的wen字编辑功能。如果开发者想要一个可以编辑的使用编辑内容的组件EditText。
  不仅如此，TextView还派生出了Button类。图介绍了TextView 子类
  image in 74
  TextView 属性
-------------------------------------------------
属性名称	描述
android:autoLink	设置是否当文本为URL链接/email/电话号码/map时，文本显示为可点击的链接。可选值(none/web/email/phone/map/all)
android:autoText	如果设置，将自动执行输入值的拼写纠正。此处无效果，在显示输入法并输入的时候起作用。
android:bufferType	指定getText()方式取得的文本类别。选项editable 类似于StringBuilder可追加字符，
也就是说getText后可调用append方法设置文本内容。spannable 则可在给定的字符区域使用样式，参见这里1、这里2。

android:capitalize	设置英文字母大写类型。此处无效果，需要弹出输入法才能看得到，参见EditView此属性说明。
android:cursorVisible	设定光标为显示/隐藏，默认显示。
android:digits	设置允许输入哪些字符。如“1234567890.+-*/%\n()”
android:drawableBottom	在text的下方输出一个drawable，如图片。如果指定一个颜色的话会把text的背景设为该颜色，并且同时和background使用时覆盖后者 @drawable/...。
android:background      绘制背景 可以是图片资源或者是颜色资源。
android:drawableLeft	在text的左边输出一个drawable，如图片。
android:drawablePadding	设置text与drawable(图片)的间隔，与drawableLeft、drawableRight、drawableTop、drawableBottom一起使用，可设置为负数，单独使用没有效果。
android:drawableRight	在text的右边输出一个drawable，如图片。
android:drawableTop	在text的正上方输出一个drawable，如图片。
android:editable	设置是否可编辑。这里无效果，参见EditView。
android:editorExtras	设置文本的额外的输入数据。在EditView再讨论。
android:ellipsize	设置当文字过长时,该控件该如何显示。有如下值设置：”start”—–省略号显示在开头；”end”——省略号显示在结尾；”middle”—-省略号显示在中间；”marquee” ——以跑马灯的方式显示(动画横向移动)

android:freezesText	设置保存文本的内容以及光标的位置。参见：这里。

android:gravity	设置文本位置，如设置成“center”，文本将居中显示。
android:hint	Text为空时显示的文字提示信息，可通过textColorHint设置提示信息的颜色。此属性在EditView中使用，但是这里也可以用。
android:imeOptions	附加功能，设置右下角IME动作与编辑框相关的动作，如actionDone右下角将显示一个“完成”，而不设置默认是一个回车符号。这个在EditView中再详细说明，此处无用。
android:imeActionId	设置IME动作ID。在EditView再做说明，可以先看这篇帖子：这里。

android:imeActionLabel	设置IME动作标签。在EditView再做说明。
android:includeFontPadding	设置文本是否包含顶部和底部额外空白，默认为true。
android:inputMethod	为文本指定输入法，需要完全限定名（完整的包名）。例如：com.google.android.inputmethod.pinyin，但是这里报错找不到。
android:inputType	设置文本的类型，用于帮助输入法显示合适的键盘类型。在EditView中再详细说明，这里无效果。
android:marqueeRepeatLimit	在ellipsize指定marquee的情况下，设置重复滚动的次数，当设置为marquee_forever时表示无限次。
android:ems	设置TextView的宽度为N个字符的宽度。这里测试为一个汉字字符宽度，如图： 
android:maxEms	设置TextView的宽度为最长为N个字符的宽度。与ems同时使用时覆盖ems选项。
android:minEms	设置TextView的宽度为最短为N个字符的宽度。与ems同时使用时覆盖ems选项。
android:maxLength	限制显示的文本长度，超出部分不显示。
android:lines	设置文本的行数，设置两行就显示两行，即使第二行没有数据。
android:maxLines	设置文本的最大显示行数，与width或者layout_width结合使用，超出部分自动换行，超出行数将不显示。
android:minLines	设置文本的最小行数，与lines类似。
android:linksClickable	设置链接是否点击连接，即使设置了autoLink。
android:lineSpacingExtra	设置行间距。
android:lineSpacingMultiplier	设置行间距的倍数。如”1.2”
android:numeric	如果被设置，该TextView有一个数字输入法。此处无用，设置后唯一效果是TextView有点击效果，此属性在EdtiView将详细说明。
android:password	以小点”.”显示文本
android:phoneNumber	设置为电话号码的输入方式。
android:privateImeOptions	设置输入法选项，此处无用，在EditText将进一步讨论。
android:scrollHorizontally	设置文本超出TextView的宽度的情况下，是否出现横拉条。
android:selectAllOnFocus	如果文本是可选择的，让他获取焦点而不是将光标移动为文本的开始位置或者末尾位置。TextView中设置后无效果。
android:shadowColor	指定文本阴影的颜色，需要与shadowRadius一起使用。效果：  
android:shadowDx	设置阴影横向坐标开始位置。
android:shadowDy	设置阴影纵向坐标开始位置。
android:shadowRadius	设置阴影的半径。设置为0.1就变成字体的颜色了，一般设置为3.0的效果比较好。
android:singleLine	设置单行显示。如果和layout_width一起使用，当文本不能全部显示时，后面用“…”来表示。如android:text="test_ singleLine " android:singleLine="true" android:layout_width="20dp"将只显示“t…”。如果不设置singleLine或者设置为false，文本将自动换行
android:text	设置显示文本.
android:textAppearance	设置文字外观。如“?android:attr/textAppearanceLargeInverse
”这里引用的是系统自带的一个外观，？表示系统是否有这种外观，否则使用默认的外观。可设置的值如下：textAppearanceButton/textAppearanceInverse/textAppearanceLarge/textAppearanceLargeInverse/textAppearanceMedium/textAppearanceMediumInverse/textAppearanceSmall/textAppearanceSmallInverse
android:textColor	设置文本颜色
android:textColorHighlight	被选中文字的底色，默认为蓝色
android:textColorHint	设置提示信息文字的颜色，默认为灰色。与hint一起使用。
android:textColorLink	文字链接的颜色.
android:textScaleX	设置文字之间间隔，默认为1.0f。分别设置0.5f/1.0f/1.5f/2.0f效果如下：
 
android:textSize	设置文字大小，推荐度量单位”sp”，如”15sp”
android:textStyle	设置字形[bold(粗体) 0, italic(斜体) 1, bolditalic(又粗又斜) 2] 可以设置一个或多个，用“|”隔开
android:typeface	设置文本字体，必须是以下常量值之一：normal 0, sans 1, serif 2, monospace(等宽字体) 3] 
android:height	设置文本区域的高度，支持度量单位：px(像素)/dp/sp/in/mm(毫米)
android:maxHeight	设置文本区域的最大高度
android:minHeight	设置文本区域的最小高度
android:width	设置文本区域的宽度，支持度量单位：px(像素)/dp/sp/in/mm(毫米)，与layout_width的区别看这里。

android:maxWidth	设置文本区域的最大宽度
android:minWidth	设置文本区域的最小宽度
----------------------------------------------------------
  解释几个
  1.android:autoLink属性值是如下几个值组成，如果需要多个值很简单用竖线|
    none:                              不设置任何超链接。
    web(对应于Linkify.WEB_URLS):       将wen本框中的URL地址转为超链接
    email(............EMAIL_ADDRESSES) 将wen本框中的E-mail转换为超链接
    phone(............PHONE_NUMBERS)   将wen本转化为电话超链接
    map(..............MAP_ADDRESSES)   将wen本地址转化为超链接
    all:相当于                         web|email|phone|map
  2.android:ellipsize 设置如果wen本框中的内容超出wen本框的显示范围处理值
    none:不进行任何处理
    start:在wen本的开头部分进行省略
    middle:在wen本的中间进行省略
    end:在wen本的结尾进行省略
    marquee在wen本的结尾以淡出的方式省略。
    这个省略不是拿掉而是说使用省略号。
    如果属性后的方法参数需要传float的注意属性值也需要float类的。
  XMLwen件也可以用作Drawable下的资源使用。
  例如
  布局xml
  <TextView 
      android:background="@drawable/bg_color" />
  drawable目录下面这样来定义
  bg_border.xml
  内容是
  <?xml version="1.0" encoding="UTF-8" ?>
  <shape xmlns:android="http://schemas.android.com/apl/res/android">
      <solid android:color="#000000" />
      <stroke android:width="2dip" android:color="#ff0000">
  </shape>

---------------------------------------------------------------
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android" >
    
    <!-- 圆角 -->
    <corners
        android:radius="9dp"
        android:topLeftRadius="2dp"
        android:topRightRadius="2dp"
        android:bottomLeftRadius="2dp"
        android:bottomRightRadius="2dp"/><!-- 设置圆角半径 -->
    
    <!-- 渐变 -->
    <gradient
        android:startColor="@android:color/white"
        android:centerColor="@android:color/black"
        android:endColor="@android:color/black"
        android:useLevel="true"
        android:angle="45"
        android:type="radial"
        android:centerX="0"
        android:centerY="0"
        android:gradientRadius="90"/>
    
    <!-- 间隔 -->
    <padding
        android:left="2dp"
        android:top="2dp"
        android:right="2dp"
        android:bottom="2dp"/><!-- 各方向的间隔 -->
    
    <!-- 大小 -->
    <size
        android:width="50dp"
        android:height="50dp"/><!-- 宽度和高度 -->
    
    <!-- 填充 -->
    <solid
        android:color="@android:color/white"/><!-- 填充的颜色 -->
    
    <!-- 描边 -->
    <stroke
        android:width="2dp"
        android:color="@android:color/black"
        android:dashWidth="1dp"
        android:dashGap="2dp"/>
    
</shape>

---------------------------------------------------------------
用户友好的界面
  鼠标放到wen本框上会选中已经存在的内容。放到电话框上只能输入电话号码。
  当鼠标获得焦点选取所有的内容
  <EditText
      android:hint="请输入账号"  这个是默认的提示信息，什么都没输入默认就这个。
      android:password="true" 能显示个点，想密码框那样。
      android:selectAllOnFocus="true"  当输入框获得焦点后选取所有内容。
      android:phoneNumber="true" 只能输入数字,而且囊当你放在框上，弹出的是数字键盘。
  />

按钮(Button) 与 图片按钮(ImageButton) 组件的功能和用法。
  Button 继承了TextView ImageButton 继承了 Button,不管是Button 还是 ImageButton它们的功能都很单一，主要就是在UI界面上生成一个按钮提供一个OnClick 供用户点击。然而Button 和 ImageButton区别在于，Button显示的是wen字，而ImageButton显示的是图片。
  特别说明在ImageButton上指定android:text是没有用处的，也不会有任何的内容显示。
  按钮使用期来比较容易，可以通过，android:background属性为按钮增加背景颜色或者背景图片，但这种背景图片或者颜色是固定，不会随着用户的动作改变而改变，ImageButton，图片按钮可以指定android:src属性但不能设置wen字，如果只是为ImageButton的android:src指定一张图片也是不可以随用户多动作改变。
  更强大的按钮
  实例：按钮、圆形按钮、带wen字的图片按钮。件来定义Drawable对象，再将Drawable对象设为Button的android:background值，或者为ImageButton的src属性值。
  <!--普通wen字按钮-->
  <Button 
      android:text="pt"
  />
  <!--普通图片按钮-->
  <ImageButton
      android:src="@drawable/blue"  和颜色叠加这个在上background在下
      android:background="#900000"
  />
  
  <!--按下的时候显示不同图片的按钮-->
  <ImageButton
      android:src="@drawable/button_selector"
      android:background="#000000"
  />
  <Button
      android:background="@drawable/button_select"
      android:text="带wen字的图片按钮"
  />

  button_select xml 
  <?xml version="1.0" encoding="UTF-8" ?>
  <selector xmlns:android="http://schemas.android.com/apk/res/android">
      <!--指定按钮按下时的图片-->
      <item android:state_pressed="true"
	android:drawable="@drawable/red"
      />
      <!--指定按钮松开时的图片-->
      <item android:state_pressed="false"
	android:drawable="@drawable/purple"	 
      />
   </selector>
上面资源wen件使用<selector .../>元素定义一个StateListDrawable对象
关于使用xml来定义Drawable内容后面又介绍。
如果使用图片作为背景或者是前景，如果按钮太长那么这张图会被拉伸。


使用9Path  图片作为按钮的背景
  当背景图片缩放由于是全部缩放，以保证正好合适的按钮所以可能达不到我们希望缩放图片的某个部分。为了实现这个缩放想缩放的部分使用9Path 图片来实现。
  9Path是一种特殊的PNG图片这种图片以.9.png结尾。它在原始的图片的四周各加一个像素的线条，这4条线就决定了该图片缩放的规则、内容显示的规则。
  左侧和上侧的直线共同决定了图片的缩放区域，左侧区域决定了纵向，上侧区域决定了横向。二者相交决定了在两个方向的缩放。
  右侧和下侧相交组成的为内容显示区域的矩形。
  http://jingyan.baidu.com/article/86fae346b60f633c49121a97.html 这个介绍如何使用draw9patch.bat
  这个工具存在于，sdk下面的tool里面。

单选按钮(RadioButton)和复选框(CheckBox)
  RadioButton 和 CheckBox 都继承自Button这个类
  RadioButton 和 CheckBox 都有被选中的功能所以有android:checked属性。
  该属性用于指定默认是否被选中。
  因为RadioButton通常一组只有一个被选中所以有个RadioGroup来组合使用。
  code on 85

状态开关(ToggleButton)按钮功能与用法
  ToggleButton 也继承Button
  ToggleButton和CheckBox非常相似，但是ToggleButton通常用于切换程序中的某种状态。
  下面显示ToggleButton所支持的XML属性及状态。
  1.android:checked setChecked(boolean) 设置是否选中
  2.android:textOff 设置当该按钮没有被选中时显示的wen本。
  3.android:textOn  设置当该按钮被选中的时候显示的wen本。
  code on 86
  有个事件改变状态就会触发它
  togglebutton.setOnCheckedChangeListener(new onCheckedChangeListener(){
    public void onCheckedChangeListener(CompoundButton ag0, boolean ag1){
	if(ag1){
		LinearLayout(object).setOrientaion(1) 垂直
        }else{
 		LinearLayout(object).setOrientation(0)  水平
         }
    }

   })
时钟(AnalogClock 和 DigitalClock) 的功能与用法
  时钟UI组件 DigitalClock 继承自TextView, AnalogClock 继承View
  DigtalClock会显示当前时间，可以显示秒数。
  AnalogClock 模拟的显示当前时间，它不会显示秒数，它重写了View 的 OnDraw方法

计时器组件
  Chronnometer继承自TextView 作用是计算从某个时间点开始，一共过去了多少时间。
  它有一个android:format属性用于设置计数器的计时格式。
  方法如下
  setBase(long base) 设置时间的起始点。
  setFormat(String format) 设置显示格式
  start() 开始
  stop()  停止
  setOnChronnometerTickListener(Chronnometer.OnChronnometerTickListener listener): 为计数器设定时间监听器，当计时器改变时触发该监听器。
  code on 88 line
  Chronnometer ch = (Chronnometer)findViewById(R.id....);
  button.setOnClickListener(new OnClickListener(){
    public void onClick(View e){
	ch.setBase(SystemClock.elapsedRealtime());
        ch.start();
    }
  })
  ch.setOnChronnometerTickListener(new OnChronnometerTickListener(){
	public void onChronnometerTicke(Chronnometer ch){
		//如果超过了20s就停止 这里用SystemClock.elapsedReatime()获取时间
		if(SystemClock.elapsedRealtime() - ch.getBase()){
			ch.stop();
		}
        }

  })
  
关于程序中的SystemClock类是一个获取系统事件，运行时间的工具类。可以查看API

图像视图 (ImageView) 的功能和用法.
  ImageView继承自View组建，主要用它承载图像，但是这么讲不是特别确切，因为任何Drawable对象都可以通过它来承载。
  1.android:adjustViewBounds setAdjustViewBounds 设置是否调整组件的边界来保持图片的比例。
  2.android:maxHeight setMaxHeight(int) 设置ImageView 的最大高度
  3.android:maxWidth  setMaxWidth(int)  设置ImageView 的最大宽度
  4.android:scaleType setScaleType(ImageView.ScaleType) 设置所显示的图片如何缩放或者移动以适应ImageView的大小。
  5.android:src	      setImageRresource(int) 设置ImageView 所显示的Drawable对象的Id
  
  







解释一句话该子组件：这个的意思是这个组件作为容器组件的子组件。
  
