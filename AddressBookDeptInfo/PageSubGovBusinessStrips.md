# 分页获取下一级条线列表

## 接口说明
```java
    /**
     * 分页获取下一级条线列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptPageSubGovBusinessStrips(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2348)
## 实现方法
```java
    /**
     * 分页获取下一级条线列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptPageSubGovBusinessStrips(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_PAGE_SUB_GOV_BUSINESS_STRIPS)
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("businessStripCode", jsonObject.getString("businessStripCode"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```