# 服务端通过临时授权码获取授权用户的个人信息

## 接口说明
```java
    /**
     * 服务端通过临时授权码获取授权用户的个人信息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String rpcOauth2GetUserInfoByCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2536)
## 实现方法
```java
    /**
     * 服务端通过临时授权码获取授权用户的个人信息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String rpcOauth2GetUserInfoByCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadAMBApiConstants.RPC_OAUTH2_GET_USER_INFO_BY_CODE)
                .addParameter("code", jsonObject.getString("code"))
                .addParameter("access_token", jsonObject.getString("access_token"));
        return postClient.post();
    }
```