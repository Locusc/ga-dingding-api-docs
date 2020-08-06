# 获取流程设计节点上的按钮列表

## 接口说明
```java
    /**
     * 获取流程设计节点上的按钮列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaProcessGetActivityButtonVOs(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2586)
## 实现方法
```java
    /**
     * 获取流程设计节点上的按钮列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaProcessGetActivityButtonVOs(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAProcessConstants.YIDA_PROCESS_GET_ACTIVITY_BUTTON_VOS)
                .addParameter("activityId", jsonObject.getString("activityId"))
                .addParameter("processCode", jsonObject.getString("processCode"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```