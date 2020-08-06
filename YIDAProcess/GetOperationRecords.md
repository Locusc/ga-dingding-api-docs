# 获取审批记录

## 接口说明
```java
    /**
     * 获取审批记录
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessGetOperationRecords(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2583)
## 实现方法
```java
    /**
     * 获取审批记录
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessGetOperationRecords(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_GET_OPERATION_RECORDS)
                .addParameter("processInstanceId", jsonObject.getString("processInstanceId"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```