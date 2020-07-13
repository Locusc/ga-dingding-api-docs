# get_jsapi_token.json

## 接口说明
```java
    /**
     * /get_jsapi_token.json JSAPI鉴权
     * @param accessToken
     * @return java.lang.String
     **/
    String getJsApiToken(String accessToken);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2493)
## 实现方法
```java
    /**
     * /get_jsapi_token.json JSAPI鉴权
     * @param accessToken accessToken
     * @return java.lang.String
     **/
    @Override
    public String getJsApiToken(String accessToken) {
        PostClient postClient = this.newGadPostClient(GadJsApiAuthConstants.GET_JS_API_TOKEN);
        if(StringUtils.isNotEmpty(accessToken)) {
            postClient.addParameter("accessToken", accessToken);
        } else {
            throw new GadNullPointerException("accessToken is empty in getJsApiToken");
        }
        return postClient.post();
    }
```