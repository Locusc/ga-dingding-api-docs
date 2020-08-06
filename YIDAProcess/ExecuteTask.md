# 执行单个任务接口

## 接口说明
```java
    /**
     * 执行单个任务接口
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessExecuteTask(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2582)
## 实现方法
```java
    /**
     * 执行单个任务接口
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessExecuteTask(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_EXECUTE_TASK)
                .addParameter("outResult", jsonObject.getString("outResult"))
                .addParameter("noExecuteExpressions", jsonObject.getString("noExecuteExpressions"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("formDataJson", jsonObject.getString("formDataJson"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("remark", jsonObject.getString("remark"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("procInstId", jsonObject.getString("procInstId"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("taskId", jsonObject.getString("taskId"));
        return postClient.post();
    }
```