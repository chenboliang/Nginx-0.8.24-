Nginx-0.8.24-
=============

Nginx是一款高性能的web服务器。目前开发版本为0.9，稳定版本为0.8，历史稳定版本为0.7。现阶段搭建版本为Nginx-0.8.24。
Nginx优点
    Nginx重点就是性能的优化。在访问峰值，或者恶意发起慢连接会导致服务器资源耗尽。而nginx采取了分阶段资源分配技术，使得它的CPU与内存的占用率非常低。官方表示保持1W个没有活动的连接，它只占用2.5M内存，所以基于以上情况及类似于DOS这样的攻击对nginx来说是毫无用处。

能够支持高达50000个并发连接数的响应，在高并发的环境下Nginx是个不错的选择。

   Nginx作为负载均衡的服务器，具体的配置见下面叙述。Nginx 既可以在内部直接支持 Rails 和 PHP 程序对外进行服务，也可以支持作为 HTTP代理服务器对外进行服务。Nginx采用C进行编写，不论是系统资源开销还是CPU使用效率都比 Perlbal 要好很多。

Nginx支持热部署，启动容易可以做到7*24小时不间断运行。

注意事项
由于在nginx的配置文件用到了正则表达式，所在在安装nginx之前要确保系统中已经正确安装了pcre。

************************

一定要保证你的linux环境下正确安装了gcc，否则在使用make命令的时候报错的。

************************
Pcre的安装
webget   ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre-8.01.tar.gz

tar  zxvf  pcre-8.01.tar.gz

cd  pcre-8.01

./configure

make

make  install


Nginx的安装
Tomcat6和Jdk1.6的安装与环境变量的配置这里不再赘述。

1.     下载Nginx文件。

webget  文件链接/nginx-0.8.24.tar.gz

拷贝文件到某一目录

2.     解压文件

tar  zxvf   nginx-0.8.24.tar.gz

cd  nginx-0.8.24

3.     编译和安装文件

设置编译文件的存放目录（看网上大多数都说把编译后的文件存放到一个单独的目录中去，挺好的方便管理）：

./configure  --prefix = /usr/local/nginx-0.8.24

make

make  install

在终端没有提示出现什么错误即是安装成功。

在浏览器中输入127.0.0.1回车，页面中显示Welcome   to  nginx！表示安装成功。

Nginx的启动
cd  /usr/local/nginx-0.8.24/sbin

./nginx

如果在第三步骤没有指定设置编译文件的存放目录，那么nginx的启动方式如下：

cd   安装目录/objs

./nginx
