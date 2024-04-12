### 静态资源访问


可以自定义静态资源过滤策略
在application.properties中直接定义过滤规则和静态资源位置：

```java
spring.mvc.static-path-pattern=/static/**
spring.web.resources.static-locations=classpath:/static/
```


### 文件上传原理


表单的enctype属性跪地给再发送到服务器之前应该如何对表单数据进行编码

表单的enctype="application/x-www-form-urlencoded"(默认)时，form表单中的数据格式为：key=value&key=value

当表单的enctype="multipart/form-data"时，会有特殊的传输数据形式


### SpringBoot实现文件上传功能


Spring Boot工程嵌入的tomcat限制了请求的文件大小，每个文件的配置最大为1Mb，单次请求的文件的总数不能大于10Mb。

要更改这个默认值需要在配置文件(如application.properties)中加入两个配置

```java
spring.servlet.multipart.max-file-size=10MB
spring.servlet.multipart.max-request-size=10MB
```


### SpringBoot实现文件上传功能


当表单的enctype="multipart/form-data"时，可以使用MultipartFile获取上传的文件数据，再通过transferTo方法将其写入到磁盘中