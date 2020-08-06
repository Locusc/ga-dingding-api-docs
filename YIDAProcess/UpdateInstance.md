# 流程实例更新

## 接口说明
```java
    /**
     * 流程实例更新
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessUpdateInstance(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2585)
## 实现方法
```java
    /**
     * 流程实例更新
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessUpdateInstance(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_UPDATE_INSTANCE)
                .addParameter("processInstanceId", jsonObject.getString("processInstanceId"))
                .addParameter("updateFormDataJson", jsonObject.getString("updateFormDataJson"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("ignoreEmpty", String.valueOf(jsonObject.getBoolean("ignoreEmpty")))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```