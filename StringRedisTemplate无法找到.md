## StringRedisTemplate 无法找到

>使用 stringredistemplate 的时候，启动服务发现提示说这个包一直找不到。
>检查后发现redis 已经成功被导入，在实现类中的对象也成功被注入，但是仍然出现问题.
>最后在 stact overflow 上找到了解决方法，是因为高版本的 redis 缺少了 jedis 包，所以在 pom 中引入 jedis。

### Description：


```
Description:

Field redis in cn.xdl.ovls.user.service.UserServiceImpl required a bean of type 'org.springframework.data.redis.core.StringRedisTemplate' that could not be found.


Action:

Consider defining a bean of type 'org.springframework.data.redis.core.StringRedisTemplate' in your configuration.

```

### Solve:

```
    		<!-- redis 缓存 -->
		<dependency>
			<groupId>org.springframework.data</groupId>
			<artifactId>spring-data-redis</artifactId>
			<!-- <version>1.5.1.RELEASE</version> -->
		</dependency>

    		<!-- jedis -->
		<dependency>
			<groupId>redis.clients</groupId>
			<artifactId>jedis</artifactId>
			<!-- <version>2.7.3</version> -->
		</dependency>
```
