# 查询定义的事件列表

## 接口说明
```java
    /**
     * 查询定义的事件列表
     * @return java.lang.String
     **/
    String messageQueryCallbackDefine();
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2309)
## 实现方法
```java
    /**
     * 查询定义的事件列表
     * @return java.lang.String
     **/
    @Override
    public String messageQueryCallbackDefine() {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_QUERY_CALLBACK_DEFINE);
        return postClient.post();
    }
```