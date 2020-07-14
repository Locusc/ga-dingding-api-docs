# 根据行政区划Code列表查询

## 接口说明
```java
    /**
     * 根据行政区划 Code 列表查询
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptListDivisionsByCodes(JSONObject jsonObject);

```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2349)
## 实现方法
```java
    /**
     * 根据行政区划 Code 列表查询
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptListDivisionsByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_LIST_DIVISIONS_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        if(StringUtils.isNotEmpty(jsonObject.getString("divisionCodes"))) {
            postClient.addParameter("divisionCodes", jsonObject.getString("divisionCodes"));
        } else if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("divisionCodes"))){
            jsonObject.getJSONArray("divisionCodes").forEach(code -> {
                postClient.addParameter("divisionCodes", String.valueOf(code));
            });
        }
        return postClient.post();
    }
```