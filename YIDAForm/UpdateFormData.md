# 更新单据中指定组件值

## 接口说明
```java
    /**
     * 更新单据中指定组件值
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaFormUpdateFormData(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2588)
## 实现方法
```java
    /**
     * 更新单据中指定组件值
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaFormUpdateFormData(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAFormConstants.YIDA_FORM_UPDATE_FORM_DATA)
                .addParameter("useLatestVersion", String.valueOf(jsonObject.getBoolean("useLatestVersion")))
                .addParameter("updateFormDataJson", jsonObject.getString("updateFormDataJson"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("formInstId", jsonObject.getString("formInstId"))
                .addParameter("ignoreEmpty", String.valueOf(jsonObject.getBoolean("ignoreEmpty")))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```