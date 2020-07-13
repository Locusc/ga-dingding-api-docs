# 取消待办接口

## 接口说明
```java
    /**
     * 取消待办任务
     * @param cancelPakcage 同步处理实例
     * @param userId 用户ID
     * @param taskUuid 任务唯一ID
     * @return java.lang.String
     **/
    String tcOpenApiTaskCancel(Boolean cancelPakcage, String userId, String taskUuid);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2286)
## 实现方法
```java
    /**
     * 取消待办任务
     * @param cancelPakcage 同步处理实例
     * @param userId 用户ID
     * @param taskUuid 任务唯一ID
     * @return java.lang.String
     **/
    @Override
    public String tcOpenApiTaskCancel(Boolean cancelPakcage, String userId, String taskUuid) {
        PostClient postClient = this.newGadPostClient(GadToDoApiConstants.TC_OPEN_API_TASK_CANCEL)
                .addParameter("cancelPakcage", String.valueOf(cancelPakcage))
                .addParameter("userId", userId)
                .addParameter("taskUuid", taskUuid);
        return postClient.post();
    }
```