# 查询待办任务

## 接口说明
```java
    /**
     * 查询待办任务
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessGetTodoTasksInCorp(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2595)
## 实现方法
```java
    /**
     * 查询待办任务
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessGetTodoTasksInCorp(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDATaskCenterConstants.YIDA_PROCESS_GET_TODO_TASKS_IN_COPY)
                .addParameter("taskFinishTo", String.valueOf(jsonObject.getLong("taskFinishTo")))
                .addParameter("corpId", jsonObject.getString("corpId"))
                .addParameter("instanceCreateFrom", String.valueOf(jsonObject.getLong("instanceCreateFrom")))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("token", jsonObject.getString("token"))
                .addParameter("createFrom", String.valueOf(jsonObject.getLong("createFrom")))
                .addParameter("processCodes", jsonObject.getString("processCodes"))
                .addParameter("taskFinishFrom", String.valueOf(jsonObject.getLong("taskFinishFrom")))
                .addParameter("createTo", String.valueOf(jsonObject.getLong("createTo")))
                .addParameter("limit", String.valueOf(jsonObject.getInteger("limit")))
                .addParameter("page", String.valueOf(jsonObject.getInteger("page")))
                .addParameter("appTypes", jsonObject.getString("appTypes"))
                .addParameter("keyword", jsonObject.getString("keyword"))
                .addParameter("instanceCreateTo", String.valueOf(jsonObject.getLong("instanceCreateTo")))
                .addParameter("status", jsonObject.getString("status"));
        return postClient.post();
    }
```