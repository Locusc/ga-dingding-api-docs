# 获取租户根组织

## 接口说明
```java
    /**
     * 根据租户ID获取租户根组织
     * @param tenantId 租户ID
     * @return java.lang.String
     **/
    String deptGetRootOrganization(Long tenantId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2289)
## 实现方法
```java
    /**
     * 根据租户ID获取租户根组织
     * @param tenantId 租户ID
     * @return java.lang.String
     **/
    @Override
    public String deptGetRootOrganization(Long tenantId) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_GET_ROOT_ORGANIZATION)
                .addParameter("tenantId", String.valueOf(tenantId));
        return postClient.post();
    }
```