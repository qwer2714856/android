1.java android ���Ĵ����
  Activity
  Service
  BroadcastReceiver
  ContentProvider

2.�ܹ�
  androidƽ̨���� ����ϵͳ(�ײ��ǽ�����linux��)���м�����û����桢Ӧ����������
  androidϵͳ�����
  Ӧ�ó���㣨����Ӧ�á���ϵͳ����Ӧ�ã�����sms�����Զ��忪����Ӧ�ã�
  Ӧ�ó����ܣ��ṩ�˴�����API��������ʹ�ã�
  �����⣨c/c++�Ŀ⼯�ϣ������߲���ֱ�ӵ��ã���Ҫͨ��Ӧ�ó����ܵ�API����
  Android����ʱ��java���Ŀ⼯��Dalvik�������ÿ��android���������ڵ�����һ��Dalvik��android����java��д�ģ�������Щ�˻��Dalvik �������java��jvm���������˵�ʵ����Dalvikû����ѭjvm�Ĺ淶������Ҳ�����ݣ�java��jvm�����е�java���ֽ���ͨ������.class file ��jar���е��ֽ��� Dalvikû�а취ֱ�Ӵ�.class��jar file�ж�ȡ�ֽ��룬����ҪDX���߽�Ӧ�ó��������е�.class file�����.dex file Dalvik ����.dex file��
  linux�ں�
  android ϵͳ������linux 2.6֮�ϡ�

  sdk��Ŀ¼
  add-ons:   ��Ŀ¼�´�Ŷ���ĸ������������Ÿ��ӿ�����GoogleMaps�����google api �İ汾��
  platforms: ��Ŀ¼��Ų�ͬ�汾��android�汾������ϵͳ����
  tools:     ��Ŀ¼�´���˴�����android���������Թ��ߡ�
  SDK Manager�ó������android sdk �� AVD�Ĺ�������
  doc:       ��Ŀ¼�����android sdk ����file��api�ȵ�
  platfrom-tools: ��Ŀ¼�����androidƽ̨��صĹ��ߡ�
  sample:    ��Ŀ¼��Ų�ͬ��androidƽ̨��ʾ������
  Ϊ���������п���ֱ��ʹ��android sdk �ĸ��ֹ��߽���tools �� platfrom-tools����path
�ϵİ�װ����
  sdk->eclipse->adt
  ����sdk��װ ����eclipse��װ ����adtȻ����eclipse���氲װhelp->install new software->����sdkװ��eclipse����window->preferences->android->ѡ��sdk�İ�װ·����
   eclipse download http://www.eclipse.org
   adt download     http://developer.android.com/sdk/eclipse-adt.html
   sdk              http://developer.android.com/sdk/index.html

Android ���õĿ������ߵ��÷�
  ����� genymotion �پ����Դ�����avd���и�interl���٣�
  ��������
  android list ��ʾ���е�android�汾�Լ�������װ��adt
  android list avd ��ʾ���а�װ��avd
  android list target ��ʾ�����Ѿ���װ��android�汾
  android create avd -n<avd name> -t<android version> -p<avd�豸����·��> -s<ѡ��avdƤ��> ����һ��avd�豸 ��-n -t �Ǳ�ѡ�-p�����дĬ���� ANDROID_SDK_HOME�Ļ��������д�� ���� android create avd -n leegang -t 6(6��android 2.3�Ĵ���)��
  android move avd �ƶ���������һ��AVD�豸
  android delete avd ɾ��һ��AVD�豸
  android update avd ����һ��AVD�豸ʹ֮ƥ���µ�SDK����
  android create test-project ����һ���µ�android������Ŀ
  android update test-project ����һ�����е�android������Ŀ
%ANDROID_SKD_HOME%/androidĿ¼
  hi.avd hi.ini hi avd �Ļ�����Ϣ��AVD�豸������hi.avd Ŀ¼����һ��userdata.img file , ����avd���û����ݾ��񡣻���һ��sdcard.img,���Ǹ�avd���õ�����sd���ľ���
android ģ������Emulator��
  android ģ��������һ�������ڵ����ϵ������ֻ�
  emulator �������� emulator -avd <AVD����>
  ���磺emulator -avd hi
  emulator -data ����file����
  ���磺emulator -data myfile��Ϊ����file������AVD�豸
ʹ��DDMS���е���
  �豸��壺DDMS�������Ͻǵ���壬�������г��������е�ģ���������г�����ģ�����ڲ������н�����Ϣ�������Ҫָ��ģ������Ϣ��Ӧ���ڸ������ѡ��ָ��ģ��������̡�  ��Ϣ�����壺�����λ��DDMS�·����ǳ���Ҫ���൱��java�Ŀ���̨
  �̸߳�����壺�����������ڲ鿴ָ����������������ִ�е�״̬�������ʵ����״̬1���thread 2���豸���ѡ����Ҫ�鿴�Ľ��̡�
  Heap�ڴ������壺��ʾ���ڴ�ͷ���ͻ�����Ϣ�����heap�����豸���ѡ����Ҫ�鿴���̡�
  ģ����������壺���������ģ��������绰�����Ͷ��ŵȣ���������������ģ������λ����Ϣ�ȡ�����绰���������Ҫ�������ģ����emulator�����и���������ž��У������׾Ϳ������������Ƶ��
  file����Ի��򣺸öԻ���Ĭ��û����ʾ����������ͨ����������Device->file Expleorer�Ϳɿ�������fileϵͳ
  ���eclipse��װ��ADT���Ĭ�ϻἯ��DDMS�ģ�eclipse���Ͻ��С����ߵ�����windows->show view->other�Ϳ��ԡ�
  �ھ�������������Ϣ�����˵�����Ϣһ����tab����
Android Debug Bridge(ADB)�÷�
  adb����ʵ�ֵ��Ժ������֮��Ŀ�����Ҳ�����л���androidϵͳʹ��linux�����װӦ��apk����platform-tools�����һ�����ߡ�
  adb�����
  adb devices �г���ǰ�������е�ģ������
  ������ģ����֮���file�໥����, 
  adb push d:/abc.txt /sdcard/ ��d:\abc.txt���Ƶ�/sdcard/����ȥ
  adb pull /sdcard/syz.txt d:/ ��sdcard�µ����ݸ��Ƶ�d:������
  shell
    adb shell ����android��shell ����
  ��װ��ж��apk����
  ���APK����������
    1.ͨ��DX���߶�*.class file����ת����ת����ͨ���õ�һ��*.dex file
    2.ͨ��AAPT���ߴ�����е���Դfile,�����ͨ���õ�*.ap_file
    3.ͨ��apkbuild��12�õ���*.dex *.ap_ file�����apk��
  adb install -r -s 
    1.-r ��ʾ���°�װapk
    2.-s ����������豸��������emulator-5554
  adb install aaa.apk -r -s emulator-5554
  ж��apk adb uninstall -k package
  1.-k ��ʾֻɾ��Ӧ�ó��򣬵������ó�������ݺͻ���Ŀ¼��
  ע�������package��data������Ǹ�package���ֲ���Ӧ�õ����ơ�

DX���빤��
  dalvik���еĲ���java�Ķ�����file���������Լ���.dex file, ���������Ҫʹ��DX��.class file �����.dex file
  DX���ߵĳ��������ʽ����
  dx --dex [--dump-to=<file>] [--core-library] [<file>.class | <file>.{zip,jar,apk}|<dierctory>]
  �����������[--dump-to<file>] ָ���������.dex  file��·����--core-library����Ҫ�����.class .zip .jar file ����Ŀ¼
  dx --dex --dump-to=d:\aa.dex --core-library d:\aaa\bin
  ��aaaĿ¼�µ����ж�����file�������aa.dex��

AAPT����
  ������android��ʱ��Ӧ�ÿ��ܻ��õ��ܶ����Դ���������ֵ�ͼƬ��Ƶ���ʱ�������跢����һ��apk��ʱ����Ҫ����Դ���.ap_
  ��ص�ָ��
    1.aapt l �г���Դѹ�����ڵ����ݡ� 
    2.aapt d �鿴apk���ڵ�ָ�����ݡ�
    3.aapt p ���������Դѹ������
    4.aapt r ��ѹ������ɾ��ָ��file��
    5.aapt a ��ѹ���������ָ��file
    6.aapt v ��ӡAAPT�İ汾��
���ָ��
  aapt -A <������Դ��·��> -S <��Դ·��> -M <AndroidӦ���嵥file> -I<������ӵİ�> -F Ŀ��file��·����
  ����
  aapt -A assets -S res -M AndroidManifest.xml -I d:\...\...\platforms\android-9\atforms\android-9\android.jar -F bin\res.ap_
 �����ָ���ǰĿ¼�µ�assets��Ŀ¼��res��Ŀ¼, AndroidManifest.xml file������� bin\res.ap_��Դ���С�

ʹ��mksdcard���������SD��
  ����ǰ����android sdk �� avd�����м��������ǿ����ڴ���avd�豸ʱ����һ������sd����ʵ���ϻ�����ʹ��mksdcard����������������һ������洢����
  mksdcard ��������
  mksdcard [-l label] <size> <file>
  �����������<size> ָ������SD���Ĵ�С,<file>ָ����������SD����file����
  mksdcard 64M d:\avd\sdcard.img
  ���ϣ��ģ����ʹ�������SD��������Ҫ������ģ�������-sdcard <file>ѡ�����<file>����������SD���ľ���
  emulator -avd aaa -sdcard d:\avd\sdcard.img
