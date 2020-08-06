# 宜搭附件地址转临时免登地址

## 接口说明
```java
    /**
     * 宜搭附件地址转临时免登地址
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaFileGetOpenUrl(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2597)
## 实现方法
```java
    /**
     * 宜搭附件地址转临时免登地址
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaFileGetOpenUrl(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAOtherConstants.YIDA_FILE_GET_OPEN_URL)
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("fileUrl", jsonObject.getString("fileUrl"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("timeout", String.valueOf(jsonObject.getLong("timeout")));
        return postClient.post();
    }
```