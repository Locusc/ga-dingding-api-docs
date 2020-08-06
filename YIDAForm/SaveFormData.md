# 新增单据实例

## 接口说明
```java
    /**
     * 新增单据实例
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaFormSaveFormData(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2587)
## 实现方法
```java
    /**
     * 新增单据实例
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaFormSaveFormData(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAFormConstants.YIDA_FORM_SAVE_FORM_DATA)
                .addParameter("instValue", jsonObject.getString("instValue"))
                .addParameter("noExecExp", String.valueOf(jsonObject.getBoolean("noExecExp")))
                .addParameter("formUuid", jsonObject.getString("formUuid"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("formInstId", jsonObject.getString("formInstId"))
                .addParameter("formDataJson", jsonObject.getString("formDataJson"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```