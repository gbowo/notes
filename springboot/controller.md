### 路由映射：接收前端请求


@RequestMapping 主要负责URL的路由映射,他可以添加在Controller类或具体的方法上,如果添加在Controller类上
则该Controller所有的路由映射都将会加上此映射规则，如果添加在方法上则只对当前方法生效
@RequestMapping常用属性参数:
value:请求URL的路径，支持URL模板，正则表达式；method:HTTP请求方法；consumes：请求的媒体类型，如application/json
produces：响应的媒体类型；params，headers:请求的参数及请求头的值


@RequestMapping的value属性用于匹配URL映射，value支持简单表达式
@RequestMapping支持使用通配符匹配URL，用于统一映射某些URL规则类似的请求
符号“*”匹配任意字符，“**”匹配任意路径，“？”匹配单个字符
有通配符的优先级低于没有通配符的，有“**”通配符的优先级低于有“*”通配符的优先级


HTTP请求Method有GET、POST、PUT、DELETE等方式，HTTP支持的全部Method


如果请求的只是页面和数据，使用@Controller注释即可；如果只是请求数据，则可以使用@RestController注解
默认情况下，@RestController注解会返回对象数据转换为JSON格式


@RequestParam将请求参数绑定到控制器的方法参数上，接受的参数来自HTTP请求体或请求URL的QueryString
@PathVariable:用于处理动态的URL，URL的值可以作为控制器中处理方法的参数
@RequestBody接收的参数来自于requestBody中，用于粗粒非Content-Type：application/x-www-form-urlencoded编码
格式的数据，如application/json，application/xml等类型的数据


httplocalhost:8080/hello
httplocalhost:8080/hello?nickname=zhangsan&phone=123