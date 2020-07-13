# 关闭实例接口

## 接口说明
```java
    /**
     * 关闭实例接口
     * @param userId 用户ID
     * @param packageUuid 实例唯一ID
     * @return java.lang.String
     **/
    String tcOpenApiPackageClose(String userId, String packageUuid);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2287)
## 实现方法
```java
    /**
     * 关闭实例接口
     * @param userId 用户ID
     * @param packageUuid 实例唯一ID
     * @return java.lang.String
     **/
    @Override
    public String tcOpenApiPackageClose(String userId, String packageUuid) {
        PostClient postClient = this.newGadPostClient(GadToDoApiConstants.TC_OPEN_API_PACKAGE_CLOSE)
                .addParameter("userId", userId)
                .addParameter("packageUuid", packageUuid);
        return postClient.post();
    }
```