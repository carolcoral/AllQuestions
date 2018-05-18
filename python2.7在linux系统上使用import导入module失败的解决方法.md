## python2.7在linux系统上使用import导入module失败的解决方法

因为我是直接创建的python project项目，所以我把这个配置信息放在我的入口文件中的。
在我的入口文件的头部写上以下代码即可：

        import os
        import sys
        def path_real():
            pwd = os.getcwd()
            # 当前文件的父路径
            father_path = os.path.abspath(os.path.dirname(pwd) + os.path.sep + ".")
            sys.path.append(father_path)
        def __init__():
            path_real()
