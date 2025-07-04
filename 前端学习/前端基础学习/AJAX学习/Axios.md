# Axios的基础引用法
1. 引入axios
2. 创建axios实例
   axios({
    url: 'xxx',    // 请求地址,就是你发送请求时候的地址
   }).then(res => {
    这里写一些对结果的操作方法，从接口返回的数据都在res里面
   })


# 关于Url的介绍
1. Url是uniform resource locator的缩写，中文翻译为统一资源定位符。
2. Url是互联网上资源的地址，比如百度的网址是：
                            https://www.baidu.com/api/index
3. 其中https是协议，www.baidu.com是域名，/api/index就是资源路径
   协议是钥匙，域名是地址，资源路径是家中具体方位。
4. Url的组成：协议://域名/资源路径（文件名?参数1=值1&参数2=值2&参数3=值3）
                                                  ？后面相当于添加了限制条件
        由于这样不美观，所以我们一般这样写：
            axios({
                url: 'https://www.baidu.com/api/index'
                params: {
                    参数1: 值1,
                    参数2: 值2,
                    参数3: 值3
                (注：若参数名和值（一般是变量）是相同名字，比如参数1: 参数1，你就可以只写一个参数1)
                }
            }).then(res => {
                这里写一些对结果操作的方法
            })
5. 番外：如果你返回的是一个数组，你想把他变成字符串，你可以这样：
                        return res.data.join('@')  
        这里的@是任意的字符串，你可以自己定义。@会放在每一个数组元素中间





# 常见请求方法
        重新认识一下axios里的常用配置项
        axios({
            method: 'XXX',
            url: '/XX/XX',
            data: {},  <----如果是对象，会默认给你转成json数据
            params: {}
        })
1. get请求（axios的默认请求，如果是get，可以不写method那一项）
   获取数据
   不区分大小写！   
   
2. post请求
   发送数据

3. put请求
   修改数据（全部）

4. delete请求
   删除数据

5. patch请求
   修改数据（部分）



# 错误处理
axios({
//请求选项
}).then(res => {
//处理成功
}).catch(err => {
//处理失败
})

  请求报文
   四个部分：1.请求行（请求方式还有url） 
           2.请求头（自动生成的） 
           3.空行 
           4.请求体（你传过去的内容）

  响应报文
   四个部分：1.响应行（响应状态码） 
           2.响应头（自动生成的）
           3.空行
           4.响应体（服务器返回的内容）
    
    响应码：
    1. 1xx：临时响应，表示请求已经接受，需要继续处理
    2. 2xx：成功响应，表示操作成功完成
    3. 3xx：重定向，表示需要重定向到新的url
    4. 4xx：客户端错误，表示请求包含语法错误或者无法完成请求  （比如url写错了）
    5. 5xx：服务器错误，表示服务器在处理请求的过程中发生错误
    6. 6xx：未知错误，表示服务器在处理请求的过程中发生未知错误
   

# 关于html的补充1
  <!DOCTYPE html> 这个标签是告诉浏览器，用html5标准来渲染页面
  <html lang="zh-CN"> 这个标签，表示这个页面是中文的
  <meta charset="UTF-8"> 这个标签，表示这个页面的字符编码是UTF-8
  <meta http-equiv="X-UA-Compatible" content="IE=edge"> 这个标签，表示这个页面兼容IE浏览器
  <meta name="viewport" content="width=device-width, initial-scale=1"> 这个标签，表示这个页面的宽度是设备宽度，初始缩放比例是1






