今天在写python代码的时候出现了想要把获取的json数据和其他数据形成新的dict类型的数据的时候，使用print输出一直都是unicode的编码形式。

先上解决代码：

        # 获取对象数据
        response = urllib2.open(url)
        # 格式化获取的json对象数据
        res = json.load(response)
        # key1 key2分别是我想要获取的json数据中的指定的对象
        res_req1 = res[key1]
        res_req2 = res[key2]
        # 重点来了
        # 根据获取的数据形成了新的dict类型数据
        res_req = {res_req1:res_req2}
        # 主要就是下面这句话，把我们的unicode类型的数据转换成可以识别的中文
        res_req = json.dumps(res_req,encoding='utf8',ensure_ascii=False)
        # 打印
        print res_req
        
Python 中的中文若在没有处理的时候会识别成 unicode 格式，当我们使用 IDEA 进行编译的时候会直接转码，但是当我们需要用这个数据形成新的数据的时候，编译器就会把这串 unicode 编码识别成字符串直接写入新数据集中。
    
