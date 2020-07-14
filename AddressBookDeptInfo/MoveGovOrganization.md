# 移动组织

## 接口说明
```java
    /**
     * 移动组织
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptMoveGovOrganization(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2302)
## 实现方法
```java
    /**
     * 移动组织
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptMoveGovOrganization(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_MOVE_GOV_ORGANIZATION)
                .addParameter("organizationCode", jsonObject.getString("organizationCode"))
                .addParameter("parentCode", jsonObject.getString("parentCode"))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```