# 终止流程实例

## 接口说明
```java
    /**
     * 终止流程实例
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessTerminateInstance(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2581)
## 实现方法
```java
    /**
     * 终止流程实例
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessTerminateInstance(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_TERMINATE_INSTANCE)
                .addParameter("processInstanceId", jsonObject.getString("processInstanceId"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```