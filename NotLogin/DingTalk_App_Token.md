# 根据authCode获取登录token

## 接口说明
```java
    /**
     * 根据authCode获取登录token
     * @param accessToken 应用access_token
     * @param authCode 临时授权码
     * @return java.lang.String
     **/
    String rpcOauth2DingTalkAppToken(String accessToken, String authCode);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2376)
## 实现方法
```java
    /**
     * 根据authCode获取登录token
     * @param accessToken 应用access_token
     * @param authCode 临时授权码
     * @return java.lang.String
     **/
    @Override
    public String rpcOauth2DingTalkAppToken(String accessToken, String authCode) {
        PostClient postClient = this.newGadPostClient(GadLoginApiConstants.RPC_OAUTH2_DINGTALK_APP_TOKEN);
        if(StringUtils.isEmpty(accessToken)) {
            throw new GadNullPointerException("accessToken is empty in rpcOauth2DingTalkAppToken");
        } else {
            postClient.addParameter("access_token", accessToken);
        }
        if(StringUtils.isEmpty(authCode)) {
            throw new GadNullPointerException("authCode is empty in rpcOauth2DingTalkAppToken");
        } else {
            postClient.addParameter("auth_code", authCode);
        }
        return postClient.post();
    }
```