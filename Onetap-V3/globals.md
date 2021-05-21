# 全局变量Globals

- <a href="#Global">Global</a>
- [Globals](#Globals)
- [Sound](#Sound)
- [Cheat](#Cheat)
- [Local](#Local)
- [World](#World)
- [Input](#Input)
- [Render](#Render)
- [UI](#UI)
- [Convar](#Convar)
- [Event](#Event)
- [Entity](#Entity)
- [Trace](#Trace)
- [UserCMD](#UserCMD)
- [AntiAim](#AntiAim)
- [Exploit](#Exploit)
- [Ragebot](#Ragebot)
- [Material](#Material)



------



## <a id="Global">Global</a>

> 不建议使用此模块,Global仅是单纯地从其他模块链接到现有的函数，因此完全不需要。

```javascript
Global.Print(string)
```

此为Cheat.Print的别名,使用Cheat.Print替代







## <a id="Globals">Globals</a>





## <a id="Cheat">Cheat</a>

### Cheat.**Print**(text: [`string`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String))

打印文本到CSGO控制台

换行符`\n`需手动添加





### Cheat.**PrintChat**(text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

打印文本到聊天框（只有本人能看到）

可使用颜色代码改变文本颜色

| Byte | Color    |      | Byte | Color         |      | Byte | Color |      | Byte | Color        |
| ---- | -------- | ---- | ---- | ------------- | ---- | ---- | ----- | ---- | ---- | ------------ |
| \x01 | White    |      | \x05 | Lighter green |      | \x09 | Gold  |      | \x0D | Dark purple  |
| \x02 | Dark red |      | \x06 | Light green   |      | \x0A | Gray  |      | \x0E | Light purple |
| \x03 | Purple   |      | \x07 | Red           |      | \x0B | Aqua  |      | \x0F | Light red    |
| \x04 | Green    |      | \x08 | Gray          |      | \x0C | Blue  |      |      |              |

使用示例：

```javascript
Cheat.PrintChat(" \x06以 \x08" + Cheat.GetUsername() + " \x06登录 \x01Cheak:\x08Successful\x01\n");
```

```javascript
Cheat.PrintChat(" \06welcome to \x01Future\x06Sense\x01.uno \x01\n")
```

可以看到，示例中**在第一个字符串前都加了空格。**

这是因为第一个字符不能是改变颜色的字节，在字符串的开始添加一个空格可以修复这个问题





### Cheat.**PrintColor**(color: [`RGBA`](https://leodev.xyz/csgo/onetap/v3/docs/types.html#RGBA), text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

以**四色模式**打印文本到CSGO控制台

使用示例

```
Cheat.PrintColor( [ 255, 0, 0, 255 ], "这是一个红色演示数据" );
```



### Cheat.**GetUsername**(): [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

获取steam用户名

使用示例：

```javascript
var username = Cheat.GetUsername();
Cheat.PrintColor([255,215,0, 255], " ​" + "\n")
Cheat.PrintColor([255,215,0, 255], "          •> Welcome To MI"+"XO-"+"YAW <•" + "\n");
Cheat.PrintColor([255,215,0, 255], "          •> Discord: Mix"+"ologi"+"st#6"+"105 ​<•" + "\n");
Cheat.PrintColor([255,215,0, 255], "          •> Log"+"ged in as: " + username + " <• \n");
Cheat.PrintColor([255,215,0, 255], "          •> Last upd"+"ate: 4/"+"11/"+"20"+"21 <• \n");
```





### Cheat.**RegisterCallback**(callback: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), func: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

**将func回调注册给函数callback,使callback在调用后执行func处理函数**

CSGO官方函数[查看](https://wiki.alliedmods.net/Counter-Strike:_Global_Offensive_Events)

具体用法在[Callbacks](Onetap-V3/Callbacks.md)文档查看更多信息

- callback: 欲监控的函数名
- func :回调函数名字符串

使用示例：

```javascript
//函数名必须全局声明
function crazyInverter(){
    // this gets called every tick
	if(!UI.IsHotkeyActive("Script items","Crazy Inverter")) return;
	if(crazy_Inverter++ === crazy_Inverter_speed){
		UI.ToggleHotkey("Anti-Aim", "Fake angles", "Inverter");
		crazy_Inverter = 0;
	}
}
......
//回调
Global.RegisterCallback("CreateMove", "crazyInverter");

```

### Cheat.**ExecuteCommand**(command: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))













