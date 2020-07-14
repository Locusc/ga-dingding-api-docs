# 分页获取下一级组织Code列表

## 接口说明
```java
    /**
     * 分页获取下⼀级组织 Code 列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptPageSubOrganizationCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2290)
## 实现方法
```java
    /**
     * 分页获取下⼀级组织 Code 列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptPageSubOrganizationCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_PAGE_SUB_ORGANIZATION_CODES)
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("status", jsonObject.getString("status"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```