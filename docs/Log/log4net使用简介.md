## .NET��־��¼֮����log4net���ص�ƪ
### 1.����
log4net��.Net��һ���ǳ�����Ŀ�Դ��־��¼�����log4net��¼��־�Ĺ��ܷǳ�ǿ�������Խ���־�ֲ�ͬ�ĵȼ����Բ�ͬ�ĸ�ʽ���������ͬ��ý�顣

### 2.Log4net����Ҫ��ɲ���
#### 2.1 **Appenders**
Appenders����������־�������ʽ������־Ҫд�����ֽ�����ȥ���ϳ��õ�Log4net�Ѿ�ʵ�ֺ��ˣ�ֱ���������ļ��е��ü��ɣ��ɲμ����������ļ����ӣ���ȻҲ�����Լ�дһ������Ҫ��log4net.Appender.AppenderSkeleton��̳С���������ͨ������Filters��Layout��ʵ����־�Ĺ��˺������ʽ��

�Ѿ�ʵ�ֵ������ʽ�У�
```
AdoNetAppender ����־��¼�����ݿ��С����Բ���SQL�ʹ洢�������ַ�ʽ��

AnsiColorTerminalAppender ����־���������ANSI�նˡ�

AspNetTraceAppender  ����asp.net��Trace�ķ�ʽ�鿴��¼����־��

BufferingForwardingAppender ���������Appenders֮ǰ�Ȼ�����־�¼���

ConsoleAppender ����־�����Ӧ�ó������̨��

EventLogAppender ����־д��Windows Event Log��

FileAppender ����־������ļ���

ForwardingAppender ������־�¼�����Appenders��

LocalSyslogAppender ����־д��local syslog service (������UNIX������)��

MemoryAppender ����־�浽�ڴ滺������

NetSendAppender ����־�����Windows Messenger service.��Щ��־��Ϣ�����û��ն˵ĶԻ�������ʾ��

OutputDebugStringAppender ����־�����Debuger���������û��Debuger���������ϵͳDebuger�����ϵͳDebugerҲ�����ã���������Ϣ��

RemoteSyslogAppender ͨ��UDP����Э�齫��־д��Remote syslog service��

RemotingAppender ͨ��.NET Remoting����־д��Զ�̽��նˡ�

RollingFileAppender ����־�Իع��ļ�����ʽд���ļ��С�

SmtpAppender ����־д���ʼ��С�

SmtpPickupDirAppender ����Ϣ���ļ��ķ�ʽ����һ��Ŀ¼�У���IIS SMTP agent������SMTP����Ϳ����Ķ��������ǡ�

TelnetAppender �ͻ���ͨ��Telnet��������־�¼���

TraceAppender ����־д��.NET trace ϵͳ��

UdpAppender ����־��������UDP���ݱ�����ʽ�͵�Զ����������UdpClient����ʽ�㲥��

```

#### **2.2 Filters**

ʹ�ù��������Թ��˵�Appender��������ݡ�������ͨ�������¼��֣�
```
DenyAllFilter ��ֹ���е���־�¼�����¼

LevelMatchFilter ֻ��ָ���ȼ�����־�¼��ű���¼

LevelRangeFilter ��־�ȼ���ָ����Χ�ڵ��¼��ű���¼

LoggerMatchFilter ��Logger����ƥ�䣬�ż�¼

PropertyFilter ��Ϣƥ��ָ��������ֵʱ�ű���¼

StringMathFilter ��Ϣƥ��ָ�����ַ����ű���¼
```

#### **2.3 Layouts**

Layout���ڿ���Appender�������ʽ�����������Ե�Ҳ������XML��

һ��Appenderֻ����һ��Layout��

��õ�LayoutӦ���Ǿ����ʽ��PatternLayout�������SimpleLayout��RawTimeStampLayout��ExceptionLayout��Ȼ����IRawLayout��XMLLayout�ȼ�����ʹ�ý��١�Layout�����Լ�ʵ�֣���Ҫ��log4net.Layout.LayoutSkeleton��̳У������һЩ������Ҫ�ĸ�ʽ���ں�����չʱ������ʵ����һ��Layout��
```
SimpleLayout �������ʽ��ֻ�����־��������Ϣ���ݡ�

RawTimeStampLayout ������ʽ��ʱ�䣬�������ݿ����ʱ���õ�����ʽ�硰yyyy-MM-dd HH:mm:ss��

ExceptionLayout ��Ҫ��Logger�ķ�������Exception������Ϊ�����������ã������ʲôҲ������������ʱ������Message��Trace��

PatternLayout ʹ������һ��Layout�����������Ϣ�ܶ࣬ʹ�÷�ʽ�ɲμ����������е������ļ���PatterLayout�ĸ�ʽ���ַ������ĺ�ע8.1��
```

#### **2.4 Loggers**

Logger��ֱ�Ӻ�Ӧ�ó��򽻻��������Loggerֻ�ǲ�����־��Ȼ���������õ�Appender��¼��ָ����ý�飬����Layout���������ʽ��

Logger�ṩ�˶��ַ�ʽ����¼һ����־��Ϣ��Ҳ�����ж��Loggerͬʱ���ڡ�ÿ��ʵ������Logger����Ա�log4net��Ϊ����ʵ�壨Named Entity����ά����log4netʹ�ü̳���ϵ��Ҳ����˵�����������Logger�����ֱַ�Ϊa.b.c��a.b����ôa.b����a.b.c�����ȡ�ÿ��Logger���̳��������ȵ����ԡ����е�Logger����Root�̳�,Root����Ҳ��һ��Logger��

��־�ĵȼ��������ɸߵ��׷ֱ�Ϊ��
```
OFF &gt; FATAL &gt; ERROR &gt; WARN &gt; INFO &gt; DEBUG  &gt; ALL 
```

���ڵȼ��趨ֵ������������òμ��������ļ���⡱������д����־�� Off���е�д�뷽������д����־�ALL���෴�����統�������Infoʱ��logger.Debug�ͻᱻ���Զ���д���ļ�������FATAL,ERROR,WARN,INFO�ᱻд�룬��Ϊ���ǵȼ�����INFO��

�ھ���д��־ʱ��һ��������������־�ȼ���
```
FATAL���������󣩣���¼ϵͳ�г��ֵ���ʹ��ϵͳ��ȫʧȥ���ܣ�����ֹͣ��ϵͳ������ʹϵͳ�޷�����������ȥ�Ĵ������磬���ݿ��޷����ӣ�ϵͳ������ѭ����

ERROR��һ����󣩣���¼ϵͳ�г��ֵĵ���ϵͳ���ȶ������ֹ��ܳ��ֻ��һ򲿷ֹ���ʧЧһ��Ĵ������磬�����ֶ�Ϊ�գ����ݲ���������ɣ����������쳣�ȡ�

WARN�����棩����¼ϵͳ�в�Ӱ��ϵͳ�������У���������ϵͳ���������������п�������ϵͳ�������Ϣ�����磬��¼����Ϊ�գ��������ݲ���ȷ�ȡ�

INFO��һ����Ϣ������¼ϵͳ������Ӧ�����û�֪���Ļ�����Ϣ�����磬����ʼ���У������Ѿ������ȡ�

DEBUG ��������Ϣ������¼ϵͳ���ڵ��Ե�һ����Ϣ�����ݻ�����һЩ�ؼ��������ݵ������
```
Loggerʵ�ֵ�ILog�ӿڣ�ILog������5��������Debug,Inof,Warn,Error,Fatal���ֱ�Բ�ͬ����־�ȼ���¼��־����5����������5�����ء���DebugΪ��˵��һ�£������ĺ�����ࡣ

ILog�ж�Debug�����Ķ������£�
```
void Debug(object message);

void Debug(object message, Exception ex);
```
����һ���������ԣ�
```
bool IsDebugEnabled { get; }
```
���ʹ��Debug(object message, Exception ex)��������Layout���Ƿ�����%exception��Ĭ����������־�������Exception������Exception��Message��Trace�����ʹ��Debug(object message)������־�ǲ������Exception��

���Ҫ˵һ��LogManager�࣬�������������е�Logger������GetLogger��̬���������Ի�������ļ�����Ӧ��Logger��
```
log4net.ILog log = log4net.LogManager.GetLogger("logger-name");
```

#### **2.5 Object Renders**

��������logger��ΰ�һ������ת��Ϊһ���ַ�����¼����־���ILog�ж���Ľӿڽ��յĲ�����Object��������String����

���������Orange�����¼����־�У�����ʱloggerֻ�����OrangeĬ�ϵ�ToString�������ѡ�����Ҫ����һ��OrangeRender��ʵ��log4net.ObjectRender.IObjectRender�ӿڣ�Ȼ��ע�����������ڱ����е���չ��ʹ�����ַ���������ֱ��ʵ��һ���Զ����Layout������ʱlogger�ͻ�֪����ΰ�Orange��¼����־���ˡ�

#### **2.6 Repository**

Repository��Ҫ������־������֯�ṹ��ά����

### 3.�����ļ����

#### **3.1 �����ļ�����**

��Ҫ�����󲿷֣�һ������һ����Ϊ��log4net�����Զ������ýڣ�������ʾ��
```
&lt;configSections&gt;
    &lt;section name="log4net" type="log4net.Config.Log4NetConfigurationSectionHandler, log4net" /&gt;
&lt;/configSections&gt;
&lt;log4net&gt;
    ...
    ...
    ...
&lt;/log4net&gt;
```
����&lt;log4net&gt;�ڵľ������ã���������Ҫ�ص�˵���ġ�
#### 3.1.1 &lt;log4net&gt;

���е����ö�Ҫ��&lt;log4net&gt;Ԫ���ﶨ�塣

֧�ֵ����ԣ�

���� | ��� 
------------- | -------------
 debug | ��ѡ��ȡֵ��true��false��Ĭ����false������Ϊtrue������log4net���ڲ����ԡ� 
 update | ��ѡ��ȡֵ��Merge(�ϲ�)��Overwrite(����)��Ĭ��ֵ��Merge������ΪOverwrite�����ύ���õ�ʱ��������Ѿ����ù��Ŀ⡣ 
 threshold | ��ѡ��ȡֵ��repository���⣩��ע���level��Ĭ��ֵ��ALL�� 

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
appender | 0����
logger | 0����
renderer | 0����
root | ���һ��
param | 0����

#### 3.1.2 &lt;root&gt;

ʵ���Ͼ���һ����logger����������logger��Ĭ�ϼ̳�������������ļ���û����ʽ���壬����ʹ�ø���־�ж�������ԡ�rootԪ��û�����ԡ�

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
appender-ref | 0��������Ҫ���õ�appender�����֡�
level | ���һ���� ֻ������������֮�ϵ��¼��Żᱻ��¼��
param | 0�������� ����һЩ������

#### 3.1.3 &lt;logger&gt;
֧�ֵ����ԣ�

���� | ��� 
- | :-:
name | ����ģ�logger������
additivity | ��ѡ��ȡֵ��true��false��Ĭ��ֵ��true������Ϊfalseʱ����ֹ��logger�е�appender��

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
appender-ref | 0��������Ҫ���õ�appender�����֡�
level | ���һ���� ֻ������������֮�ϵ��¼��Żᱻ��¼��
param | 0�������� ����һЩ������

#### 3.1.4 &lt;appender&gt;
������־�������ʽ��ֻ����Ϊ log4net ����Ԫ�ء�name���Ա���Ψһ��type���Ա���ָ����

֧�ֵ����ԣ�

���� | ��� 
- | :-:
name | ����ģ�Appender���������
type | ����ģ�Appender������������

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
appender-ref | 0�������������appender��������appender������������appender���Ͷ�֧�֡�
filter | 0�������������appʹ�õĹ�������
layout | ���һ��������appenderʹ�õ������ʽ��
param | 0�������� ����Appender���ж�Ӧ�����Ե�ֵ��

ʵ����&lt;appender&gt;���ܰ�������Ԫ��Զ��ֹ����4����

#### 3.1.5 &lt;layout&gt;

���֣�ֻ����Ϊ&lt;appender&gt;����Ԫ�ء�

֧�ֵ����ԣ�

���� | ��� 
- | :-:
type | ����ģ�Layout������

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
param | 0�������� ����һЩ������

#### 3.1.6 &lt;filter&gt;
��������ֻ����Ϊ&lt;appender&gt;����Ԫ�ء�

֧�ֵ����ԣ�

���� | ��� 
- | :-:
type | ����ģ�Filter������

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
param | 0�������� ����һЩ������

#### 3.1.7 &lt;param&gt;

&lt;param&gt;Ԫ�ؿ������κ�Ԫ�ص���Ԫ�ء�

֧�ֵ����ԣ�

���� | ��� 
- | :-:
name | ����ģ�ȡֵ�Ǹ�����Ĳ�������
value | ��ѡ�ģ�value��type�У�������һ�����Ա�ָ����value��һ���ܱ�ת��Ϊ����ֵ���ַ�����
type | ��ѡ�ģ�value��type�У�������һ�����Ա�ָ����type��һ�������������type������log4net�����ж���ģ�����Ҫʹ��ȫ����

֧�ֵ���Ԫ�أ�

���� | ��� 
- | :-:
param | 0�������� ����һЩ������

### 4. ���������ļ�

log4netĬ�Ϲ�������Ӧ�ó���������ļ�App.config(BS������Web.config)������ʹ�ó����Զ����������������á�����������һ������Զ������ԣ�

log4net.Config.XmlConifguratorAttribute

XmlConfiguratorAttribute��3�����ԣ�

ConfigFile�� �����ļ������֣��ļ�·�������Ӧ�ó���Ŀ¼

(AppDomain.CurrentDomain.BaseDirectory)��ConfigFile���Բ��ܺ�ConfigFileExtension����һ��ʹ�á�

ConfigFileExtension�� �����ļ�����չ�����ļ�·�������Ӧ�ó����Ŀ¼��ConfigFileExtension���Բ��ܺ�ConfigFile����һ��ʹ�á�

Watch�� �����Watch��������Ϊtrue���ͻ���������ļ����������ļ������仯��ʱ�򣬾ͻ����¼��ء�

���ConfigFile��ConfigFileExtension��û�����ã���ʹ��Ӧ�ó���������ļ�App.config��Web.config����

��������Ŀ��AssemblyInfo.cs�ļ���������µ���䣺

```

//����Ĭ�ϵ������ļ���App.config 
[assembly: log4net.Config.XmlConfigurator(Watch = true)]

//ʹ�������ļ�log4net.config�������Ӹı䡣ע��log4net.config�ļ���Ŀ¼��BS������վ��Ŀ¼//�£�CS����Ӧ�ó�������Ŀ¼�£������ʱ��/bin/Debug�£�һ�㽫�ļ����Ե��ļ����Ŀ¼��Ϊ//ʼ�ո��Ƽ���

[assembly: log4net.Config.XmlConfigurator(ConfigFile = "log4net.config")]


//ʹ�������ļ�log4net.config�������Ӹı�

[assembly: log4net.Config.XmlConfigurator()]
```
 

Ҳ������Global.asax��Application_Start�������Program.cs�е�Main��������ӣ�ע������һ���Ǿ���·����������ʾ��
```
//������BS�����£�ʹ���Զ���������ļ�log4net.config��ʹ��Server.MapPath("~") + //@"/log4net.config����ȡ��·����/log4net.configΪ�����վ���·��

// ConfigureAndWatch()�൱��Configure(Watch = true)

log4net.Config.XmlConfigurator.ConfigureAndWatch(new System.IO.FileInfo(Server.MapPath("~") + @"/log4net.config"));
```
```
//������CS�����£����������·�����ã�

string assemblyFilePath = Assembly.GetExecutingAssembly().Location;

string assemblyDirPath = Path.GetDirectoryName(assemblyFilePath);

string configFilePath = assemblyDirPath + " //log4net.config";

log4net.Config.XmlConfigurator.ConfigureAndWatch(new FileInfo(configFilePath));
```
��ֱ��ʹ�þ���·����
```
//ʹ���Զ���������ļ���ֱ�Ӿ���·��Ϊ��c:/log4net.config

log4net.Config.XmlConfigurator.Configure(new System.IO.FileInfo(@"c:/log4net.config"));
```
 
&lt;/font&gt;