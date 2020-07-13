# 获取应用access_token

## 接口说明
```java
    /**
     * 获取应用access_token
     * @return java.lang.String
     **/
    String rpcOauth2GetToken();
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2354)
## 实现方法
```java
    /**
     * 获取应用access_token
     * @return java.lang.String
     **/
    @Override
    public String rpcOauth2GetToken() {
        PostClient postClient = this.newGadPostClient(GadLoginApiConstants.RPC_OAUTH2_GET_TOKEN)
                .addParameter("appKey", gadExecutableClientProperties.getAccessKey())
                .addParameter("appSecret", gadExecutableClientProperties.getSecretKey());
        return postClient.post();
    }
```