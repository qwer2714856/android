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
  
  
