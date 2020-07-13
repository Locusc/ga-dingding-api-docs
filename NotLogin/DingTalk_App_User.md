# 根据authCode换取用户信息

## 接口说明
```java
    /**
     * 根据authCode换取用户信息
     * @param accessToken 应用access_token
     * @param authCode 临时授权码
     * @return java.lang.String
     **/
    String rpcOauth2DingTalkAppUser(String accessToken, String authCode);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2375)
## 实现方法
```java
    /**
     * 根据authCode换取用户信息
     * @param accessToken 应用access_token
     * @param authCode 临时授权码
     * @return java.lang.String
     **/
    @Override
    public String rpcOauth2DingTalkAppUser(String accessToken, String authCode) {
        PostClient postClient = this.newGadPostClient(GadLoginApiConstants.RPC_OAUTH2_DINGTALK_APP_USER);
        if(StringUtils.isEmpty(accessToken)) {
            throw new GadNullPointerException("accessToken is empty in rpcOauth2DingTalkAppUser");
        } else {
            postClient.addParameter("access_token", accessToken);
        }
        if(StringUtils.isEmpty(authCode)) {
            throw new GadNullPointerException("authCode is empty in rpcOauth2DingTalkAppUser");
        } else {
            postClient.addParameter("auth_code", authCode);
        }
        return postClient.post();
    }
```