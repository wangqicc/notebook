###1 Spring 框架各层作用

####1.1 entity层

**别名：** model层 ，domain层

**用途：** 实体层，用于存放我们的实体类，与数据库中的属性值基本保持一致，实现set和get的方法。

**例子：** user表的实体User

####1.2 mapper层

**别名：** dao层

**用途：** 对数据库进行数据持久化操作，他的方法语句是直接针对数据库操作的，主要实现一些增删改查操作，在mybatis中方法主要与与xxx.xml内相互一一映射。如果方法较多的话，可以采用MyBatisGenerator自动生成xml映射文件。

**示例：** userMapper

####1.3 service层

**用途：** 业务service层，给controller层的类提供接口进行调用。一般就是自己写的方法封装起来，就是声明一下，具体实现在serviceImpl中。

**示例：** UserService

```html
service
    impl
    UserService
```

####1.4 controller层

**别名：** web 层

**用途：** 控制层，负责具体模块的业务流程控制，需要调用service逻辑设计层的接口来控制业务流程。因为service中的方法是我们使用到的，controller通过接收前端H5或者App传过来的参数进行业务操作，再将处理结果返回到前端。

**示例：** UserController

### 参考文档

[1] https://blog.csdn.net/u011095110/article/details/86088976
 
[2] https://juejin.cn/post/6844903982582743048