# 搜索流程实例ID

## 接口说明
```java
    /**
     * 搜索流程实例ID
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessGetInstanceIds(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2578)
## 实现方法
```java
    /**
     * 搜索流程实例ID
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessGetInstanceIds(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_GET_INSTANCE_IDS)
                .addParameter("modifiedFrom", jsonObject.getString("modifiedFrom"))
                .addParameter("formUuid", jsonObject.getString("formUuid"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("dynamicOrder", jsonObject.getString("dynamicOrder"))
                .addParameter("searchFieldJson", jsonObject.getString("searchFieldJson"))
                .addParameter("useOriginValue", jsonObject.getString("useOriginValue"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("instanceStatus", jsonObject.getString("instanceStatus"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("createFrom", jsonObject.getString("createFrom"))
                .addParameter("targetFieldJson", jsonObject.getString("targetFieldJson"))
                .addParameter("approvedResult", jsonObject.getString("approvedResult"))
                .addParameter("createTo", jsonObject.getString("createTo"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("originatorId", jsonObject.getString("originatorId"))
                .addParameter("currentPage", String.valueOf(jsonObject.getInteger("currentPage")))
                .addParameter("taskId", jsonObject.getString("taskId"))
                .addParameter("modifiedTo", jsonObject.getString("modifiedTo"));
        return postClient.post();
    }
```