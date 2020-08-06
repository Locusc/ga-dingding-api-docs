# 根据单据实例ID查询单据实例详情

## 接口说明
```java
    /**
     * 根据单据实例ID查询单据实例详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaFormGetFormDataById(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2590)
## 实现方法
```java
    /**
     * 根据单据实例ID查询单据实例详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaFormGetFormDataById(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAFormConstants.YIDA_FORM_SEARCH_FORM_DATA_BY_ID)
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("formInstId", jsonObject.getString("formInstId"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("needInstValue", String.valueOf(jsonObject.getBoolean("needInstValue")));
        return postClient.post();
    }
```