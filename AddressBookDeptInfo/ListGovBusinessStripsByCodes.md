# 根据条线Code列表查询

## 接口说明
```java
    /**
     * 根据条线 Code 列表查询
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptListGovBusinessStripsByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2346)
## 实现方法
```java
    /**
     * 根据条线 Code 列表查询
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptListGovBusinessStripsByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_LIST_GOV_BUSINESS_STRIPS_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        if(StringUtils.isNotEmpty(jsonObject.getString("businessStripCodes"))) {
            postClient.addParameter("businessStripCodes", jsonObject.getString("businessStripCodes"));
        } else if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("businessStripCodes"))){
            if(jsonObject.getJSONArray("businessStripCodes").size() <= 100) {
                jsonObject.getJSONArray("businessStripCodes").forEach(code -> {
                    postClient.addParameter("businessStripCodes", String.valueOf(code));
                });
            } else {
                throw new GadIndexOutOfBoundsException("The length of the businessStripCodes is over 100 in deptListGovBusinessStripsByCodes");
            }
        }
        return postClient.post();
    }
```