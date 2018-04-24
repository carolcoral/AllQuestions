## linux 系统下 mysql 出现版本冲突
* 解决方案：
    
 * 1.进入 mysql；
    
 * 2.select @@sql_mode;
    
 * 3.复制出现的那段话；
    
 * 4.vi /etc/my.conf
    
 * 5.添加一个句话：sql_mode='刚才复制的那段话，不要引号'
    
 * 6.重启 mysql 服务
