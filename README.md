# Elec Room Info: SCUT 宿舍水电空调余额提醒

🥵**你还在因半夜空调欠费被热醒而困扰吗？**
😣**你是否因忘充电费突然停电而对正在运行的实验感到痛苦？**
🌟 **这份宿舍水电空调余额提醒程序能够解决你的烦恼！**

本项目支持实时跟踪宿舍水电空调余额，通过多种方式进行预警推送（微信、邮件、Pushplus、Telegram），同时支持用电日报、自定义推送等功能，帮助省去定时检查余额的麻烦。

如果你对本项目的开发感兴趣，欢迎联系并加入开发，我们需要你的支持！

---

## **功能介绍**

### 当前版本 v0.3.0
- **实时监控宿舍水电空调余额**
- **多种方式推送余额不足报警**
  - Wxpusher 微信推送
  - Pushplus 微信推送
  - Telegram Bot 推送
  - 邮件推送
- **定时用电日报**

## **准备工作**
1. 宿舍水电空调已绑定至一卡通系统->保证查询接口可用。
2. 获取 Bearer Token：
   - 登录[校园一卡通网站](https://ecardwxnew.scut.edu.cn/plat-pc/login)，通过统一认证和一卡通登录。
   - 登录完了？打开F12，转到Application，点击Session storage，查看access_token字段，复制备用。[示例图](./asserts/example.png)

## **快速开始**
本项目需要你决定运行方式（通过Github自动运行或本地运行）和发送消息给你的方式（邮件，Telegram Bot，微信Pusher，Plusplus，或者自定义）。
发送给你消息方式需要配置的细节可以在[docs/sender.md](docs/sender.md)找到，你需要配置才能发送消息，下面也会介绍。

## 基于Github Action自动运行
这种方法不需要任何设备，通过Github Action定期运行代码来达成轮询的效果。
1. fork这个仓库
2. 设置你环境变量
   > Github -> Settings -> Secrets and variables -> Actions -> New repository secret
3. 在其中配置`BEARER_TOKEN`, `SENDER_TYPE`和sender对应的相关参数。

## 本地运行
1. 修改.env.sample为.env，在里面填写`BEARER_TOKEN`, `SENDER_TYPE`和sender对应的相关参数。
2. 运行下面命令安装uv并且同步环境
```bash
    pip install uv # if you have pip
    uv sync
    uv run main.py
```
