# 流程发起

## 接口说明
```java
    /**
     * 流程发起
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessStartInstance(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2577)
## 实现方法
```java
    /**
     * 流程发起
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessStartInstance(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_START_INSTANCE)
                .addParameter("instValue", jsonObject.getString("instValue"))
                .addParameter("formUuid", jsonObject.getString("formUuid"))
                .addParameter("processCode", jsonObject.getString("processCode"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("formDataJson", jsonObject.getString("formDataJson"))
                .addParameter("deptId", jsonObject.getString("deptId"))
                .addParameter("businessId", jsonObject.getString("businessId"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("useOriginInstValue", String.valueOf(jsonObject.getBoolean("useOriginInstValue")));
        return postClient.post();
    }
```