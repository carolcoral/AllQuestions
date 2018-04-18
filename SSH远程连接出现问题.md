### 当我们重装了远程服务器的系统后，再次使用 ssh 远程连接出现以下问题：

      @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
      @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
      @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
      IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
      Someone could be eavesdropping on you right now (man-in-the-middle attack)!
      It is also possible that a host key has just been changed.
      The fingerprint for the ECDSA key sent by the remote host is
      SHA256:9ghEL/GSVFDAiI1Oh0NEIi0LNTZAidpisLIgb0XudFk.
      Please contact your system administrator.
      Add correct host key in /Users/carol/.ssh/known_hosts to get rid of this message.
      Offending ECDSA key in /Users/carol/.ssh/known_hosts:17
      ECDSA host key for 150.109.41.154 has changed and you have requested strict checking.
      Host key verification failed.
      
 ### 解决方式：
 
*Here is the simplest solution
>ssh-keygen -R <host>
* For example,
>ssh-keygen -R 192.168.3.10
