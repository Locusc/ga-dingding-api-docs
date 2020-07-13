# 查询回调失败信息

## 接口说明
```java
    /**
     * 查询回调失败信息
     * @return java.lang.String
     **/
    String messageQueryCallbackFailed();
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2312)
## 实现方法
```java
    /**
     * 查询回调失败信息
     * @return java.lang.String
     **/
    @Override
    public String messageQueryCallbackFailed() {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_QUERY_CALLBACK_FAILED);
        return postClient.post();
    }
```