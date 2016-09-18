# 360功能分析
最新版**360手机助手**提供了**MZ**的功能，能够在已经取得root权限的手机上，不调用su进行授权。

## 一、功能模块
360MZ功能主要分为**permmgr**和**rtservice**两个模块， permmgr负责加载so库，实现root提权功能； rtservice模块在permmgr获得root权限的基础上以root身份启动qh_root_service进程，appstore通过跨进行通讯控制该进程执行秒装操作。

**permmgr**模块的com.qihoo.permmgr目录下主要包括以下几个核心文件：
<table>
<tr><td>类名</td><td>作用</td></tr>
<tr><td>IPermMgrService</td><td>定义权限管理服务接口</td></tr>
<tr><td>LocalRoot</td><td>声明jni函数调用lib360.so接口</td></tr>
<tr><td>PermService</td><td>权利管理服务，监控root状态</td></tr>
<tr><td>PermManager</td><td>负责临时root方案的权限获取和so库的加载</td></tr>
</
