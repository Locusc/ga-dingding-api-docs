# 根据实例ID获取流程实例详情

## 接口说明
```java
    /**
     * 根据实例ID获取流程实例详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessGetInstanceById(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2579)
## 实现方法
```java
    /**
     * 根据实例ID获取流程实例详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessGetInstanceById(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_GET_INSTANCE_BY_ID)
                .addParameter("processInstanceId", jsonObject.getString("processInstanceId"))
                .addParameter("formUuid", jsonObject.getString("formUuid"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("useOriginValue", String.valueOf(jsonObject.getBoolean("useOriginValue")))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```