

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

### Global.**Print**(text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

此为`Cheat.Print`的别名,使用[Cheat.Print](#Cheat.Print)替代



### Global.**PrintChat**(text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

使用[Cheat.PrintChat](#Cheat.PrintChat)替代



### Global.**PrintColor**(color: [`RGBA`](https://leodev.xyz/csgo/onetap/v3/docs/types.html#RGBA), text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

使用 [Cheat.PrintColor](#Cheat.PrintColor) 替代



### Global.**RegisterCallback**(callback: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), fn: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

使用 [Cheat.RegisterCallback](#Cheat.RegisterCallback)替代



### Global.**ExecuteCommand**(command: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

使用 [Cheat.ExecuteCommand](#Cheat.ExecuteCommand) 替代



### Global.**FrameStage**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用 [Cheat.FrameStage](#Cheat.FrameStage) 替代



### Global.**Tickcount**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用  [Globals.Tickcount](#Globals.Tickcount) 替代



### Global.**Tickrate**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用 [Globals.Tickrate](#Globals.Tickrate) 替代



### Global.**TickInterval**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用 [Globals.TickInterval](#Globals.TickInterval) 替代



### Global.**Curtime**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用  [Globals.Curtime](#Globals.Curtime) 替代



### Global.**Realtime**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用 [Globals.Realtime](#Globals.Realtime) 替代



### Global.**Frametime**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用  [Globals.Frametime](#Globals.Frametime) 替代



### Global.**Latency**(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

使用 [Local.Latency](#Local.Latency) 替代



### Global.**GetViewAngles**(): [`Angle`](Onetap-V3/Types.md#Angle)

使用 [Local.GetViewAngles](#Local.GetViewAngles) 替代



### Global.**SetViewAngles**(angle: [`Angle`](Onetap-V3/Types.md#Angle))

使用  [Local.SetViewAngles](#Local.SetViewAngles) 替代



### Global.**GetMapName**(): [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

使用  [World.GetMapName](#World.GetMapName) 替代



### Global.**IsKeyPressed**(path: [`Path`](Onetap-V3/Types.md#Path)): [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

使用 [Input.IsKeyPressed](#Input.IsKeyPressed) 替代



### Global.**GetScreenSize**(): [`Vector2`](Onetap-V3/Types.md#Vector2)

使用 [Render.GetScreenSize](#Render.GetScreenSize) 替代



### Global.**GetCursorPosition**(): [`Vector2`](https://leodev.xyz/csgo/onetap/v3/docs/types.html#Vector2)

使用 [Input.GetCursorPosition](#Input.GetCursorPosition) 替代



### Global.**PlayMicrophone**(filename: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

使用 [Sound.PlayMicrophone](#Sound.PlayMicrophone) 替代



### Global.**StopMicrophone**()

使用 [Sound.StopMicrophone](#Sound.StopMicrophone) 替代



### Global.**GetUsername**(): [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

使用 [Cheat.GetUsername](#Cheat.GetUsername) 替代



### Global.**SetClanTag**(clantag: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

使用 [Local.SetClanTag](#Local.SetClanTag) 替代





------



## <a id="Globals">Globals</a>

### <a id="Globals.Tickcount">Globals.**Tickcount**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

返回服务器上已经刷新的tick值

tick指的是服务器延迟数，用来表示游戏内部状态，在1秒的时间内把玩家或敌人的动作分解为图像帧数

使用实例:

```javascript
var tickCount = Globals.Tickcount();
Cheat.Print("当前已经过去了 :" + tickCount);
```

```javascript
var old_tick_count = 0;
function Legdesync()
{
    if (UI.GetValue("Script items", "Leg desync") && (Globals.Tickcount() - old_tick_count)*4 > (UI.GetValue("Script items", "Leg desync speed")))
    {///u s e r:90
        if (UI.GetValue("Misc", "GENERAL", "Movement", "Slide walk"))
            UI.SetValue("Misc", "GENERAL", "Movement", "Slide walk", 0);
        else
            UI.SetValue("Misc", "GENERAL", "Movement", "Slide walk", 1);
        old_tick_count = Globals.Tickcount();
    }
}		
```





### <a id="Globals.Tickrate">Globals.**Tickrate**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

返回服务器上tick设定,通常为 64 或 128

使用示例:

```javascript
var tickrate = Globals.Tickrate();
Cheat.Print("服务器tick设置: " + tickrate);
```





### <a id="Globals.TickInterval">Globals.**TickInterval**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

返回每次tick时消耗的时间,单位为秒,相当于 `1/Globals.Tickrate()`

使用示例:

```javascript
var tickInterval = Globals.TickInterval();
Cheat.Print("tick耗时: " + tickInterval);
```



```javascript
//[TAIJIlogist CFG] DT充能变快
function can_shift_shot(ticks_to_shift) {
    var local_player = Entity.GetLocalPlayer();
    var wpn = Entity.GetWeapon(me);

    if (local_player == null || wpn == null)
        return false;

    var tickbase = Entity.GetProp(local_player, "CCSPlayer", "m_nTickBase");
    var curtime = Globals.TickInterval() * (tickbase-ticks_to_shift);

    if (curtime < Entity.GetProp(local_player, "CCSPlayer", "m_flNextAttack"))
        return false;

    if (curtime < Entity.GetProp(wpn, "CBaseCombatWeapon", "m_flNextPrimaryAttack"))
        return false;

    return true;
}
function _TBC_CREATE_MOVE() {
    var is_charged = Exploit.GetCharge();
   
    Exploit[(is_charged != 1 ? "Enable" : "Disable") + "Recharge"]()

    if (can_shift_shot(14) && is_charged != 1) {
        Exploit.DisableRecharge();
        Exploit.Recharge()
    }
}
function _TBC_UNLOAD() {
    Exploit.EnableRecharge();
}

```





### <a id="Globals.Curtime">Globals.**Curtime**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

返回服务器时间(以秒为单位)。即返回当前游戏已经消耗的对局时间,单位秒

使用示例:

```javascript
var curTime = Globals.Curtime();
Cheat.Print("当前游戏对局时间: " + curTime);
```

```javascript
function poggers(){
    checkRestrictions();
    coolDelay = UI.GetValue( "Script items", "Land zero delay");
    local_player = Entity.GetLocalPlayer();
    if(!Entity.IsAlive(local_player)){
        return;
    }
    if (timed1 == false) {
        lastTime1 = Globals.Curtime();///u s e r:90
        timed1 = true;
    }
    if (Globals.Curtime() > lastTime1 + .3) 
    {
        air = Entity.GetProp(local_player, "CBasePlayer", "m_flFallVelocity");
        if (air < -1 || air > 1) {
            in_air = true;
        } else {
            in_air = false;
        }
        timed1 = false;
    }
    if (Input.IsKeyPressed(0x20)){
        return;
    }
    if (lastAircheck == true && in_air==false)
    {
        if (delayedPos==0 && firstRun==false) {
            firstRun=true;///u s e r:90
        }
        runMainFunction=1;
    }
    if (runMainFunction==1){
        if (timed == false) {
            lastTime = Globals.Curtime();
            timed = true;
        }
        if (Globals.Curtime() > lastTime + coolDelay || firstRun==true) {
            if (delayedPos==1)
            { 
                UI.SetValue("Anti-Aim", "Extra", "Pitch",1);
                delayedPos=0;
                runMainFunction=0;
                timed = false;
                return;
            }  
            if (delayedPos==0)///u s e r:90
            {
                UI.SetValue("Anti-Aim", "Extra", "Pitch",3);
                delayedPos=1;
                firstRun=false;
                timed = false;
                return;
            }
        }
    }
    lastAircheck=in_air;
}
```





### <a id="Globals.Realtime">Globals.**Realtime**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

以秒为单位返回自CSGO启动后经历的时间

使用示例:

```javascript
realtime = Globals.Realtime();
```





### <a id="Globals.Frametime">Globals.**Frametime**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

返回最后一帧渲染所花费的时间。

转换为FPS使用:

```javascript
Math.floor(1 / Globals.Frametime())
```

------



## <a id="Sound">**Sound**</a>

在写了

## <a id="Cheat">Cheat</a>

### <a id="Cheat.Print">Cheat.**Print**</a>(text: [`string`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String))

打印文本到CSGO控制台

换行符`\n`需手动添加

使用示例：

```javascript
Cheat.Print( '这是一个演示数据' );
```



### <a id="Cheat.PrintChat">Cheat.**PrintChat**</a>(text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

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





### <a id="Cheat.PrintColor">Cheat.**PrintColor**</a>(color: [`RGBA`](https://leodev.xyz/csgo/onetap/v3/docs/types.html#RGBA), text: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

以**四色模式**打印文本到CSGO控制台

使用示例

```
Cheat.PrintColor( [ 255, 0, 0, 255 ], "这是一个红色演示数据" );
```



### <a id="Cheat.GetUsername">Cheat.**GetUsername**</a>(): [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

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





### <a  id="Cheat.RegisterCallback">Cheat.**RegisterCallback**</a>(callback: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), func: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

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

### <a id="Cheat.ExecuteCommand">Cheat.**ExecuteCommand**</a>(command: [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))

在CSGO控制台执行命令

- string : 欲执行的命令

使用示例：

```javascript
Cheat.ExecuteCommand( 'quit' )  //控制台执行quit指令		
```

```javascript
Cheat.ExecuteCommand("say I'm using OTC ") // 聊天框发送I'm using OTC
```





### <a id="Cheat.FrameStage">Cheat.**FrameStage**</a>(): [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

该函数用于返回OT框架当前执行状态

| Stage | Meaning                                                      |
| ----- | ------------------------------------------------------------ |
| 0     | Frame Start 框架加载                                         |
| 1     | Frame NetUpdate Start 框架在线更新启动                       |
| 2     | Frame NetUpdate PostDataUpdate Start 框架公告数据在线更新启动 |
| 3     | Frame NetUpdate PostDataUpdate End 框架公告数据在线更新结束  |
| 4     | Frame NetUpdate End 框架在线更新结束                         |
| 5     | Frame Render Start 框架渲染开始                              |
| 6     | Frame Render End 框架渲染结束                                |



使用示例:

```javascript
var currentStage = Globals.FrameStage();
Cheat.Print(currentStage);
```































