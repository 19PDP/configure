

#### 官方文档：[配置手册](https://picgo.github.io/PicGo-Doc/zh/guide/config.html)



## 配置手册

PicGo的配置文件在不同系统里是不一样的。

- Windows: `%APPDATA%\picgo\data.json`
- Linux: `$XDG_CONFIG_HOME/picgo/data.json` or `~/.config/picgo/data.json`
- macOS: `~/Library/Application\ Support/picgo/data.json`

举例，在windows里你可以在：

`C:\Users\你的用户名\AppData\Roaming\picgo\data.json`找到它。

在linux里你可以在：

`~/.config/picgo/data.json`里找到它。

macOS同理。



## 图床区

### SMMS 2.3.0+

配置项及说明：

```json
{
  "token": "" // 通过SMMS后台获取的api token值
}
```

注册并登录[smms](https://sm.ms/home/apitoken)后台获取token值。

![img](https://i.loli.net/2021/03/23/2tbeo6FWfT1HVQh.png)

