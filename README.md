protobuf-example
================
## 在线浏览本文件可能会有格式错乱，pull到本地查看则是正常的。

有通信的地方就有协议，协议描述了解析通信内容的方式。
IT中的协议一般是指解析二进制流的方式。

传统的协议解析方式是底层的、基于流的，
    例如一个MP3文件，首先它是一段二进制数据，只是以文件的形式存在与硬盘上，
    它也可以存在于内存中，或者网络传输中。
    一个播放器如果想要播放这段二进制数据，首先必须理解这段数据，
    知道那几个字节代表持续时长，那几个字节代表作者，
    那几个字节代表第一帧，那几个字节代表第二帧。。。
    知道了这些，就可以写一个MP3协议解析器了，
    有了MP3协议解析器自然也就能播放MP3协议的歌曲了

Protobuf则是高层的、基于数据结构的，或者说是面向对象的，
    它隐藏了很多繁琐的细节，可以自动生成协议解析器，
    仍以MP3协议为例，你不需要知道那几个字节代表第一帧，那几个字节代表第二帧。。。
    只需要调用自动生成的协议解析器的API就行了


如何编写proto文件？
=================

1. 官方文档https://developers.google.com/protocol-buffers/docs/overview
2. 中文教程http://hi.baidu.com/austincao/item/1663f219d96f3c1fe2f986f4



prot数据类型
===========

.proto Type	C++ Type	Java Type	Python Type

double		double		double		float
float		float		float		float
int32		int32		int			int
int64		int64		long		int/long
uint32		uint32		int			int/long
uint64		uint64		long		int/long
sint32		int32		int			int
sint64		int64		long		int/long
fixed32		uint32		int			int
fixed64		uint64		long		int/long
sfixed32	int32		int			int
sfixed64	int64		long		int/long
bool		bool		boolean		boolean
string		string		String		str/unicode
bytes		string		ByteString	str



如何编译proto文件？
=================

1. 添加protoc.exe、ProtoGen.exe、Google.ProtocolBuffers.dll到path环境变量；

2. 打开命令提示符窗口；

3. 转到mocaworld-gameserver/src/main/protos目录；

4. 编译为java，命令示例：
    protoc gameserver\network\new_server_message\protos\*.proto --java_out=.

5. 编译为c#，命令示例：
    protogen gameserver\network\new_server_message\protos\PlayerTitleProtos.proto
    google\protobuf\csharp_options.proto google\protobuf\descriptor.proto
    -ignore_google_protobuf=true
    -output_directory=csharp_out\new_server_message\protos




网络链接
=======

1. 帮助文档https://protobuf-csharp-port.googlecode.com/files/protobuf-csharp-port-2.4.1.473-help.chm

2. 二进制发布包https://protobuf-csharp-port.googlecode.com/files/protobuf-csharp-port-2.4.1.473-release-binaries.zip

3. protobuf-csharp-port项目主页https://code.google.com/p/protobuf-csharp-port/
