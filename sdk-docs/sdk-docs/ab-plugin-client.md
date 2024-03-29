# ab-plugin-client@客户端配置项

1.引入

```js
import { Client } from 'ab-plugin-client';
```

2.事件方法使用说明

> **设置主题色**

```js
let theme = '#FFF'
let result = await Client.setThemePreference(theme);

```

> **获取主题色**

```js
let result = await Client.getThemePreference();
```

> **关闭客户端**

```js
Client.closeClient().then(res => {
  // todo
});
```

> **最小化客户端**

```js
Client.setMinimized().then(res => {
  // todo
});
```

> **最大化客户端**

```js
Client.setMaxmized().then(res => {
  // todo
});
```

> **获取客户端 oid**

```js
let oid = '';
Client.getOid().then(res => {
  // todo
  oid = res.oid;
});
```

> **关机操作**

```js
Client.closeSystem().then(res => {
  // todo
});
```

> **重启操作**

```js
Client.restartSystem().then(res => {
  // todo
});
```

> **获取客户端ip**

```js
Client.getClientIp().then(res => {
  // todo
  console.log(res.clientIp)
});
```

> **获取客户端appId**

```js
let clientIp = "192.168.31.147"
Client.getAppID(clientIp).then(res => {
  // todo
  console.log(res.appId)
});
```

> **获取客户端Mac**

```js
let clientIp = "192.168.31.147"
Client.getMac(clientIp).then(res => {
  // todo
  console.log(res.mac)
});
```

> **获取配置文件内配置**

```js
let qualifier = "cn.com.agree.ab.a4.client.web";
let key = "port";
let type = "String";
let result = await Client.getProperties(qualifier,key,type);
console.log(result);
});
```

> **获取客户端根路径**

```js
Client.getClientRootPath().then(res => {
  // todo
  console.log(res.clientRootPath)
});
```

> **获取客户端操作系统名称**

```js
Client.getClientOSName().then(res => {
  // todo
  console.log(res.clientOSName)
});
```

> **获取客户端当前系统时间**

```js
let format = "yyyy-MM-dd"
Client.getClientNowSystemTime(format).then(res => {
  // todo
  console.log(res.clientNowSystemTime)
});
```

> **获取客户端文件最后修改时间**

```js
let filePath = "E:\\file.txt"
Client.getClientFileLastModified(filePath).then(res => {
  // todo
  console.log(res.clientFileLastModified)
});
```

> **客户端关闭订阅消息**

```js
Client.closeSubscribe(()=>{
  //TODO: do something to clean the cache;
  Client.closeClient();
});
```

> **创建客户端文件夹**

```js
let dir = "E:\\file.txt"
Client.makeClientDirectory(dir).then(res => {
  // todo
  console.log(res.makeClientDirectory)
});
```

> **写入客户端资源文件**

```js
let fileType = "properties"
let filePath = "E:\\aui.properties"
let charset = "utf-8"
let key = "Platform/MINA"
let value = "true"
Client.writeClientResourceFile(fileType,filePath,charset,key,value).then(res => {
  // todo
  console.log(res.writeClientResourceFile)
});
```

> **获取客户端启动参数**

```js
let argsType = "end" 返回最后一个入参
let argsType = "true" 返回符合规则的入参
其他的值和默认不传一样返回所有的值
Client.getClientStartParameters(...[argsType]).then(res => {
  // todo
  console.log(res.clientStartParameters)
});
```

> **打开客户端系统配置页**

```js
Client.openSysPage().then(res => {
  // todo
  console.log(res.clientStartParameters)
});
```

> **设置客户端通讯url**

```js
import { Client } from 'ab-plugin-client'
let name="hg";
let httpUrlList = ["http://3.1.11.76:8867"];
let aarmUrlList = ["ws://127.0.0.1:51003/websocket"];
let msgUrlList = ["ws://127.0.0.1:51004/websocket"];
let result = await Client.setCommPreference(name,httpUrlList,aarmUrlList,msgUrlList);
```

> **窗口关闭按钮是否可以关闭**

```js
let result = await Client.setShellClosable(true)
```

**Events promise 函数**

| 事件          |      说明      | 参数 |
| ------------- | :------------: | :--: |
| getThemePreference   |   获取主题色   |  -   |
| setThemePreference   |   设置主题色   |  themecolor:String主题色16进制色码   |
| closeClient   |   关闭客户端   |  -   |
| setMinimized  |  最小化客户端  |  -   |
| setMaxmized   |  最大化客户端  |  -   |
| getOid        | 获取客户端 oid |  -   |
| closeSystem   |    关机操作    |  -   |
| restartSystem |    重启操作    |  -   |
| getMac        | 获取客户端 Mac地址 |  clientIp  |
| getAppId      | 获取客户端 应用标识 |  clientIp   |
| getClientIp   | 获取客户端 客户端Ip地址    |  -   |
| getProperties   | 读取客户端配置    |  qualifier:String 插件标识前缀;key:String 配置名称;type 类型:{Boolean,String,int,double,float,long} 
| getClientRootPath   | 获取客户端根路径    |  -   |
| getClientOSName   | 获取客户端操作系统名称    |  -   |
| getClientNowSystemTime   | 获取客户端当前系统时间    |  format   |
| getClientFileLastModified   | 获取客户端文件最后修改时间    |  filePath   |
| closeSubscribe   | 关闭客户端事件订阅    |  fun:Function 关闭时触发的回调事件 |
| makeClientDirectory   | 创建客户端文件夹    |  dir   |
| writeClientResourceFile   | 写入客户端资源文件    |  fileType:客户端文件类型（目前只支持properties格式的文件）,filePath:客户端文件地址,charset:客户端文件编码,key:客户端资源文件的key,value:客户端资源文件的value |
| getClientStartParameters   | 获取客户端启动参数    |  argsType   |
| openSysPage   | 打开客户端系统配置页    |    |
| setCommPreference   | 设置客户端通讯url    |   name：oid名称, httpUrlList:aase的http的url, aarmUrlList:aarm的websocket资源更新 urlmsgUrlList:amessage的websocket消息推送url |
| getClientStartParameters   | 获取客户端启动参数    |  argsType   |
| setShellClosable        | 窗口关闭按钮是否可以关闭 |  ifClose  false 不可以关闭|true 可以关闭|
