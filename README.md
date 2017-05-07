# 2017现操期中项目

## 功能
天气app，主要功能是天气查询，辅助功能是查找城市返回地图、查找城市实时路况，通过调用高德的API实现；允许用户注册、登录，登录后使用收藏功能。高德开放平台：http://lbs.amap.com/dev/key/app  我已经注册了key（5fd3b8bd943a505ccfec387943bba945），调用API时可直接使用。
所调用的API及它们之间的关系：

| 功能 | API |
| ---  | :---: |
| 查询用户所在地的天气  | IP定位 → 天气查询 |
| 查询某个城市的天气 | 行政区划查询 → 天气查询 |
| 查城市（地区）返回对应地图 | 地理编码 → 静态地图（使用label） |
| 查城市（地区）实时交通路况 | 地理编码 → 静态地图（traffic=1） |


## 分工
### UI设计
负责设计app的页面，需要设计界面布局，页面之间的导航，自适应UI，数据绑定。
暂定为3个页面，天气查询、地图查询和登录界面，可参考win10自带的天气应用的界面。
三个页面的布局图在群里给出，里面包含了必要的控件的它们的名字，请务必使用这些名字便于前后端的统一，而如何布局不必照搬。
### 后台逻辑
细分为3部分。
1. 实现后台运行与程序生命周期、程序间通信
2. 实现磁贴、文件管理
3. 实现网络访问、数据库

## 计划用到的知识点
* 页面导航：页面之间的跳转，主要通过侧边栏实现
* 自适应UI：如天气查询页在窗口不同大小显示不同内容等
* 数据绑定：这个没什么好想法
* 后台运行与程序生命周期：挂起时保存页面信息（如查询框中的信息），重新运行后恢复信息
* 程序间通信：如分享地图、天气信息等
* 磁贴：参考之前的作业吧
* 文件管理：打开一个选择图片的filePicker，供用户选择头像
* 数据库：如用户登录后，收藏某城市，将它的信息存入数据库，用户可查找收藏的城市
* 网络访问：调用高德的API并解析，使它反馈到页面上，并有一定的异常处理
