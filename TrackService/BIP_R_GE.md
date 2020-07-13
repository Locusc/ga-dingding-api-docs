# 获取轨迹推送注册

## 接口说明
```java
    /**
     * 获取轨迹推送注册
     * @return java.lang.String
     **/
    String BipRegisterGetEvents();
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2533)
## 实现方法
```java
    /**
     * 获取轨迹推送注册
     * @return java.lang.String
     **/
    @Override
    public String BipRegisterGetEvents() {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.BIP_REGISTER_GET_EVENTS);
        return postClient.post();
    }
```