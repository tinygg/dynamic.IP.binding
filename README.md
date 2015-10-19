##作用
  没有外网静态IP的情况下,实现域名IP检测和动态绑定
  
##原理
1.  依赖DNSPOD开放接口
2.  获取当前服务器外网IP,比对域名解析的IP地址,不一致则解析为当前的外网IP地址,一致则什么也不做
3.  每次查询都会记录日志

##条件
  0. 有DNSPOD账号并且添加了独立域名
  1. 路由器做好端口映射
  2. 服务器装好python我的版本是2.7
  3. 服务器新建windows计划任务,定期执行2min比较合适  
  任务执行程序和参数:python  path-to-DNSPOD_CN_Login.py

##注意
执行频率不能过快,否则ip138.com会屏蔽你的请求...
下个版本使用APNIC查询
https://cgi1.apnic.net/cgi-bin/my-ip.php?&_=1445217586120
