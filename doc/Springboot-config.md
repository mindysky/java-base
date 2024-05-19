#### Spring boot config

application.properties>application.yml>application.yaml

-Dserver.port=8083

java -jar  java.jar  运行jar包，默认配置

#####  java系统属性配置（-Dxxx=xxx）

java -Dserver.port=9000 -jar  java.jar 

##### 命令行配置(--xxx=xxx)

java -jar  java.jar  --server.port=10010  

##### IOC容器对象

ApplicationContext

##### IOC容器获取bean对象

- 根据name获取bean: Object getBean(String name)

- 根据类型获取bean: <T> T getBean(Class<T> requiredType)
- 根据name获取bean(带类型转换)： <T> T getBean(String name, Class<T> requiredType)

##### Bean的作用域

Bean的作用域是指Bean实例的生命周期及可见性范围，Spring框架定义了以下6种作用域：

    singleton：单例作用域，所有对该Bean的请求都返回同一个Bean实例。
    prototype：原型作用域，每次请求时都创建一个新的Bean实例。
    request：请求作用域，每个HTTP请求都会创建一个新的Bean实例，该Bean实例仅在当前请求内有效。
    session：会话作用域，每个HTTP会话都会创建一个新的Bean实例，该Bean实例仅在当前会话内有效。
    application：全局作用域,一个bean 定义对应于单个ServletContext 的生命周期。
    websocket： HTTP WebSocket 作用域,一个bean 定义对应于单个websocket 的生命周期。
##### 第三方Bean的配置

```java
在配置类中对第三方类进行统一管理
//将当前方法的返回值对象交给IOC容器管理，成为IOC容器bean
//通过@Bean注解name、vaule属性指定bean的名称，如果未指定， 默认为方法名
@Bean
public SAXReader saxReader(){
	return new SAXReader();
}
```

##### SpringBoot原理



