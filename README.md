# HttpClient
HttpClient中转上传文件
#场景：
客户端(浏览器)A---->选择文件上传---->服务器B---->中转文件---->服务器C---->返回结果---->服务器B---->客户端A

有时候在项目中需要把上传的文件中转到第三方服务器，第三方服务器提供一个接收文件的接口。

而我们又不想把文件先上传到服务器保存后再通过File来读取文件上传到第三方服务器，我们可以使用HttpClient来实现。

因为项目使用的是Spring+Mybatis框架，文件的上传采用的是MultipartFile，而FileBody只支持File。

所以这里采用MultipartEntityBuilder的addBinaryBody方法以数据流的形式上传。

这里需要引入两个jar包：httpclient-4.4.jar和httpmime-4.4.jar
