# 创建待办接口V2

## 接口说明
```java
    /**
     * 创建待办接口v2
     * @param tcV2OpenApiTaskCreateObject tcV2OpenApiTaskCreateObject入参
     * @return java.lang.String
     **/
    String tcV2OpenApiTaskCreate(TcV2OpenApiTaskCreateObject tcV2OpenApiTaskCreateObject);

    /**
     * 创建待办接口v2
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String tcV2OpenApiTaskCreate(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2377)
## 实现方法
```java
    /**
     * 创建待办接口v2
     * @param tcV2OpenApiTaskCreateObject tcV2OpenApiTaskCreateObject入参
     * @return java.lang.String
     **/
    @Override
    public String tcV2OpenApiTaskCreate(TcV2OpenApiTaskCreateObject tcV2OpenApiTaskCreateObject) {
        PostClient postClient = this.newGadPostClient(GadToDoApiConstants.TC_V2_OPEN_API_TASK_CREATE)
                .addParameter("assigneeInfo", tcV2OpenApiTaskCreateObject.getAssigneeInfo())
                .addParameter("subject", tcV2OpenApiTaskCreateObject.getSubject())
                .addParameter("creatorInfo", tcV2OpenApiTaskCreateObject.getCreatorInfo())
                .addParameter("creatorId", tcV2OpenApiTaskCreateObject.getCreatorId())
                .addParameter("tenantId", tcV2OpenApiTaskCreateObject.getTenantId())
                .addParameter("bizTaskId", tcV2OpenApiTaskCreateObject.getBizTaskId())
                .addParameter("mobileUrl", tcV2OpenApiTaskCreateObject.getMobileUrl())
                .addParameter("assigneeId", tcV2OpenApiTaskCreateObject.getAssigneeId())
                .addParameter("url", tcV2OpenApiTaskCreateObject.getUrl())
                .addParameter("packageUuid", tcV2OpenApiTaskCreateObject.getPackageUuid());
        return postClient.post();
    }

    /**
     * 创建待办接口v2
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String tcV2OpenApiTaskCreate(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadToDoApiConstants.TC_V2_OPEN_API_TASK_CREATE)
                .addParameter("assigneeInfo", jsonObject.getString("assigneeInfo"))
                .addParameter("subject", jsonObject.getString("subject"))
                .addParameter("creatorInfo", jsonObject.getString("creatorInfo"))
                .addParameter("creatorId", jsonObject.getString("creatorId"))
                .addParameter("tenantId", jsonObject.getString("tenantId"))
                .addParameter("bizTaskId", jsonObject.getString("bizTaskId"))
                .addParameter("mobileUrl", jsonObject.getString("mobileUrl"))
                .addParameter("assigneeId", jsonObject.getString("assigneeId"))
                .addParameter("url", jsonObject.getString("url"))
                .addParameter("packageUuid", jsonObject.getString("packageUuid"));
        return postClient.post();
    }
```