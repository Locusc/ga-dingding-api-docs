<p align="center">
	<strong>第三方应用请求政务钉钉服务端API工具接口文档</strong>
</p>

# 项目地址
[GITHUB](https://github.com/Locusc/ga-dingding-api)
__The simple configuration, Using a simple__
## maven 引用：
```xml
    <dependency>
        <groupId>cn.locusc</groupId>
        <artifactId>ga-dingding-api-client</artifactId>
        <version>1.2.1</version>
    </dependency>
```
## application.yml 配置：
```yaml
gad:
  api:
    client:
      access-key: appKey
      secret-key: appSercet
      domain-name: 网关域名
      protocol: 协议类型
```
## 使用：
[在线访问](https://www.gad-docs.locusc.cn/)
```java
    @Resource
    public GadApiTemplate gadApiTemplate;
```
## 包含：
1. 包含官方请求SDK的功能。
2. 包含官方现有服务端API除日程外的的实现方法。

## 欢迎提交issue
如果对您有帮助，希望能给项目一个Star
## 联系作者：
QQ：2227628925
