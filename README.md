# 配置文件路径 app/src/main/assets/oneapm.properties

###############################################################################
### appKey,唯一性标志，不能忽略
OneAPMAppKey=

###############################################################################
### 服务器地址端口号，确定探针上报地址
AgentStartupPath=https://miv2dc.oneapm.com

或者

AgentStartupPath=http://miv2dc.oneapm.com

###############################################################################
### 位置信息服务器地址端口号，确定探针获取位置信息的端口，配置企业级位置url全路径即可实现
OneAPMLocationUrl=https://miv2dc.oneapm.com/services/ip?ip=myip

###############################################################################
### log级别，默认log 级别为info
LogLevel=debug


###############################################################################
### 默认会对所有的包都执行插码操作，属性 IncludePackages ExcludePackages 可以结合使用来确定 对指定的包插码，或者指定的包不插码
IncludeAllPackages=true & ExcludePackages=a.b
#### 会对所有的包插码，但是对包 a.b 不会插码
IncludeAllPackages=false & IncludePackages=a.b
#### 会对所有的包不插码，但是对包 a.b 会插码


###############################################################################
### 如果有多个包名需要添加，请用 逗号 隔开（注意区分全角半角）.
IncludePackages=com.this.pkg,com.that.pkg

#### 如果有多个包名需要添加，请用 逗号 隔开（注意区分全角半角）.

### 和阿里巴巴用户反馈webview 冲突 会造成crash
ExcludePackages=com.alibaba.sdk



###############################################################################
### Http 数据包gzip压缩功能，默认为 false 发送数据使用gzip压缩功能，如您不需要，设置为true，gzip 压缩就不会生效。

OneAPMDisableGzip=true


###############################################################################
### Crash上报设置，默认为true, 如不想上报crash，请打开注释即可

SendCrashReports=false


###############################################################################
### 您可以在此处定义您的 appName，如果appName没有在此处定义，那么会使用定义在AndroidManifest.xml 中的 application name, 作为ApplicationID
ApplicationID=com.oneapm.demo


###############################################################################
### 设置一个新的 VersionCode 和 VersionName, 如果你需要规定app的版本号，请使用此属性
VersionCode=1

VersionName=1.0


###############################################################################
### 拷贝动态连接库的开关    默认为false
CopyDynamicLibs=false

### 配置so 库的时候主要要取所有so库 ABI 的最小子集，不然在某些cpu 架构上会报错，可选项有 : 'x86', 'x86_64', 'armeabi', 'armeabi-v7a', 'arm64-v8a'多个ABI 之间用英文逗号隔开
OneApmABIFilter=armeabi

多个添加方式 

OneApmABIFilter=x86,x86_64,armeabi,armeabi-v7a

###############################################################################
### MI And AI Switch 默认为开启MI和AI 打通功能
#### false 表示 开启  MI和AI 打通功能
#### true 表示 关闭  MI和AI 打通功能
DisableAssociateWithAI=false


################################################################################
### 默认的空Action(没有子Action ,包括网络请求和actions)是不会上传的，打开注释，可以上传空Action
SendEmptyAutoAction=true


###############################################################################
### 用来控制 AutoAction 接受 child events 的时间，默认为500ms, 可配置范围 为 100ms - 5000ms

InstrumentAutoUserAction=false
AutoActionTimeoutMilliseconds=1000


### 默认情况下 AutoAction 会在 500ms 以内自动关闭 ，如果 AutoAction 发现有未完成的 子事件，
### 那么就延长自己的生命，默认延长 60000ms，通过修改 AutoActionMaxDurationMilliseconds
### 的值来修改此时间，AutoAction 在到达设置时间后，将会自动关闭

AutoActionMaxDurationMilliseconds=30000


###############################################################################
### 配置ssl, 秘钥配置，如果服务器为知名ca机构购买的证书，不用配置任何信息
### 如果你使用自签名证书，并且Android客户端有秘钥文件.bks，及秘钥密码，

BKSFileName=myKeyStore
BKSPassword=myPassword

### 如果你没有自签名秘钥，也没有CA机构颁发的证书，还要使用https，则设置AnyCert为true,
### 即可通过https 传递数据

AllowAnyCert=true

################################################################################



