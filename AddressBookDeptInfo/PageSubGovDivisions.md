# 分页获取下一级行政区划列表

## 接口说明
```java
    /**
     * 分页获取下一级行政区划列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptPageSubGovDivisions(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2351)
## 实现方法
```java
    /**
     * 分页获取下一级行政区划列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptPageSubGovDivisions(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_PAGE_SUB_GOV_DIVISIONS)
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("divisionCode", jsonObject.getString("divisionCode"))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```