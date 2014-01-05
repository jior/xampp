xampp
=====

xampp-windows(apache-2.4.7 + tomcat-7.0.47 x64位版本)

从服务器获取项目放到本地文件路径(不能包含中文)，修改如下配置文件：
1）xampp\apache\conf\httpd.conf
找到37行：
ServerRoot "E:/xampp/apache"
把这个路径修改成你的apache的目录。
2）xampp\apache\conf\extra\httpd-ajp.conf
找到10行
增加你自己的虚拟映射
如：
ProxyPass /glaf ajp://127.0.0.1:8009/glaf smax=0 ttl=60 retry=5
ProxyPass /wechat ajp://127.0.0.1:8009/wechat smax=0 ttl=60 retry=5
3）xampp\tomcat\conf\server.xml
修改147行，把其中的内容修改成你的应用的路径
<Context path="/glaf" docBase="e:/wechat/WebContent" reloadable="false"/>