# 应用注销轨迹推送

## 接口说明
```java
   /**
    * 应用注销轨迹推送
    * @param id 注册id
    * @return java.lang.String
    **/
   String BipRegisterCancell(String id);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2534)
## 实现方法
```java
    /**
     * 应用注销轨迹推送
     * @param id 注册id
     * @return java.lang.String
     **/
    @Override
    public String BipRegisterCancell(String id) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.BIP_REGISTER_CANCELL)
                .addParameter("id", id);
        return postClient.post();
    }
```