# 组织ID转换接口

## 接口说明
```java
    /**
     * 组织ID转换接口
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptZzdDeptGetDepMapByType(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2639)
## 实现方法
```java
    /**
     * 组织ID转换接口
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptZzdDeptGetDepMapByType(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_ZZD_DEPT_GET_DEP_MAP_BY_TYPE)
                .addParameter("type", jsonObject.getString("type"))
                .addParameter("departmentIds", jsonObject.getString("departmentIds"))
                .addParameter("proxyTenantId", jsonObject.getString("proxyTenantId"));
        return postClient.post();
    }
```