# Elec Room Info: SCUT 宿舍水电空调余额提醒

🥵你还在因半夜空调欠费被热醒没到服务时间无法充值所困扰吗？

😣你还在因忘充电费突然停电Boss快通关了实验跑到一半主机却关机了而痛苦吗？

🌟🌟你一定会需要的宿舍水电空调余额提醒程序！实时跟踪余额、邮件报警、充值检测、每日用电统计！再也不用定时检查余额啦！

---

如果你对我们的工作感兴趣，欢迎联系并加入后续开发！We Neeeed You!

## 功能

### v0.1.0

- [x] 水电空调余额跟踪
- [x] 余额不足报警
- [x] 充值检测
- [x] 邮件消息订阅

## 准备

- 一台长期运行的计算机，保持联网即可，不需要校园网。
- 校园一卡通web页面token（获取方式参考：企业微信 > 校园一卡通 > 复制网页链接 > 浏览器打开 > F12 Cookie > Session_ID）
- 编辑配置文件，参考[config.yaml](/sample_config.yaml)

## 快速开始

### 方式一：docker部署

构建docker镜像

`docker build -t elec_room_info:latest .`

创建运行目录

`mkdir project_dir && cd project_dir`

`mkdir data && cd data`

`mkdir configs && cd configs`

将配置文件放于`project_dir/data/configs`目录下

运行docker容器，替换容器映射路径

`docker run -v /path/to/elec_room_info:/app/data`

### 方式二：部署源代码

python 3.8

`pip install -r requirement.txt`

生成默认配置文件，须编辑完善后方可正常运行：

`python3 elec_room_info/utils/config/config_omega.py`

运行程序

`python3 elec_room_info/main.py -c config.yaml`

## Todos

- [ ] 用电日报
- [ ] 剩余水电时间估计
- [ ] 后端api
- [ ] 提供微信小程序服务
- [ ] 大学城、五山校区适配