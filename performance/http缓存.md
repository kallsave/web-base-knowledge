https://www.jb51.net/article/149001.htm

http缓存分为强制缓存和协商缓存,强制缓存的优先级大于协商缓存
http缓存是指第一次访问服务器获取数据后
在有效时间内不会再请求服务器,而是直接使用缓存数据
http1.1的优先级大于http1.0版本的缓存响应字段
即强制缓存的字段Cache-Control > Expires)
即协商缓存的字段Etag/If-None-Match > Last-Modified/If-Modified-Since

强制缓存:
在http1.0版本中
响应字段为Expires,是个绝对值
当浏览器请求时当前时间超过了Expires会到服务器取资源,否则从浏览器读取缓存
缺点是时间是客户端的时间和服务端的时间比较,不准确
是兼容写法

在http1.1版本中
响应字段为Cache-Control,有多个值
其中最常用的是max-age,max-age是以秒为单位,是缓存的相对有效值(接收到资源后倒计时的值)

协商缓存:
在http1.0版本中
响应字段为Last-Modified/If-Modified-Since
Last-Modifie是服务器颁发的资源最后的修改时间(绝对值)
If-Modified-Since是上次服务器颁发的资源的最后的修改时间
如果Last-Modifie大于If-Modified-Since,说明被修改过,则不使用缓存,否则使用缓存

在http1.1版本中
响应字段为Etag/If-None-Match
Etag是服务器颁发的标识(一般根据文件的摘要)
If-None-Match是上次服务器颁发的标识
如果Etag不等于If-None-Match,说明被修改过,则不使用缓存,否则使用缓存
