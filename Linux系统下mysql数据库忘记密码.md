<h1>Linux系统下mysql数据库忘记密码</h1>
<h2></h2>
<h2>解决方案</h2>
<p>1：首先停止mysql服务进程</p>
<pre><code>service mysqld stop
</code></pre>

<p>2：然后编辑mysql的配置文件my.cnf</p>
<pre><code>vi /etc/my.cnf
</code></pre>

<p>3：添加如下代码：</p>
<pre><code>在[mysqld]标签下：
skip-grant-tables   ##忽略mysql权限问题，直接登录
</code></pre>

<p>4：保存退出</p>
<pre><code>esc
:wq!
</code></pre>

<p>5：重启mysql数据库</p>
<pre><code>service mysqld restart
</code></pre>

<p>6：登录mysql数据库</p>
<pre><code>mysql -u root
</code></pre>

<p>7：执行如下sql语句，修改密码</p>
<pre><code>use mysql;
update user set password=password(&quot;新密码&quot;) where user=&quot;root&quot;;
flush privileges;
</code></pre>

<p>8：重启mysql服务</p>
<pre><code>service mysqld restart
</code></pre>

<p>9：使用新密码登录</p>
<pre><code>mysql -u root -p
</code></pre>
