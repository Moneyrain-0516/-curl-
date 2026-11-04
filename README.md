# -curl-
简单介绍curl的使用并举例

一、介绍：curl(Client URL)是一款功能强大的命令行工具，用于在客户端与服务器之间传输数据。它支持HTTP、HTTPS、FTP、SFTP等20多种协议，是开发者进行API调试、网络问题排查和自动化脚本编写的核心工具。


二、curl的使用：
1. 操作系统：大部分现代操作系统已经自带 curl。所以我们可以直接打开终端使用，不确定电脑是否带有curl的可以输入 curl --version 确认一下。

2.  curl 的基本语法结构：curl [选项] [URL] 。
最基础的用法就是直接写 curl 网址，它默认会向该网址发起一个 GET 请求，并将服务器返回的响应内容（如网页 HTML 代码或 JSON 数据）直接打印在终端屏幕上。如果需要增加特定功能（如查看响应头、发送 POST 数据），则在网址前加上相应的参数（选项）。

3. 例1：
以访问一个公开API为例：在终端里执行下面这行命令：curl https://httpbin.org/get
这个命令会向服务器发起 GET 请求，然后服务器返回 JSON 数据。
<img width="1108" height="454" alt="image" src="https://github.com/user-attachments/assets/3b87bfec-adde-4f18-b44a-6ce27fae775e" />

4. 例2：
再以一个带参数的请求为例：curl -I https://www.baidu.com
其中的 -I 表示只获取响应头，然后屏幕上会显示 HTTP 状态码、服务器类型等信息。
<img width="1108" height="244" alt="image" src="https://github.com/user-attachments/assets/61c8d117-3302-4d48-a737-1afa8294d6fc" />


5.  -I参数的作用：
-I（大写字母 i）参数代表 只获取 HTTP 响应头（Headers）。加上这个参数后，curl 发送的是 HEAD 请求，服务器只会返回状态码（如 200 OK）、服务器类型、内容类型、缓存设置等元数据，而不会返回网页的主体内容。这在排查网络问题、验证链接是否有效或查看服务器配置时非常高效。


三、在 API 调试中，curl 的主要用途包括：
1. 快速验证接口连通性：直接测试 API 是否能正常访问及返回状态码。
2. 测试不同请求方法：支持 GET、POST、PUT、DELETE 等，方便测试完整的增删改查逻辑。
3. 发送自定义请求头与参数：可轻松模拟携带 Token 认证（如 -H 参数）或发送 JSON 数据（如 -d 参数）。
4. 自动化与脚本集成：因为它是命令行工具，极易写入 Shell 或 Python 脚本中，用于接口自动化测试或持续集成（CI）流程。
