# 获取轨迹推送失败消息

## 接口说明
```java
    /**
     * 获取轨迹推送失败消息
     * @param eventTag 注册事件类型
     * @return java.lang.String
     **/
    String BipRegisterFailedTasks(String eventTag);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2535)
## 实现方法
```java
    /**
     * 获取轨迹推送失败消息
     * @param eventTag 注册事件类型
     * @return java.lang.String
     **/
    @Override
    public String BipRegisterFailedTasks(String eventTag) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.BIP_REGISTER_FAILED_TASKS)
                .addParameter("eventTag", eventTag);
        return postClient.post();
    }
```