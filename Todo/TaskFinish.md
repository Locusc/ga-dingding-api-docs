# 完成待办接口

## 接口说明
```java
    /**
     * 完成待办任务
     * @param closePackage 同步处理实例
     * @param userId 用户ID
     * @param taskUuid 任务唯一ID
     * @return java.lang.String
     **/
    String tcOpenApiTaskFinish(Boolean closePackage, String userId, String taskUuid);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2285)
## 实现方法
```java
    /**
     * 完成待办任务
     * @param closePackage 同步处理实例
     * @param userId 用户ID
     * @param taskUuid 任务唯一ID
     * @return java.lang.String
     **/
    @Override
    public String tcOpenApiTaskFinish(Boolean closePackage, String userId, String taskUuid) {
        PostClient postClient = this.newGadPostClient(GadToDoApiConstants.TC_OPEN_API_TASK_FINISH)
                .addParameter("closePackage", String.valueOf(closePackage))
                .addParameter("userId", userId)
                .addParameter("taskUuid", taskUuid);
        return postClient.post();
    }
```