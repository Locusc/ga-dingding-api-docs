# 根据条件搜索单据实例详情列表

## 接口说明
```java
    /**
     * 根据条件搜索单据实例详情列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaFormSearchFormDatas(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2592)
## 实现方法
```java
    /**
     * 根据条件搜索单据实例详情列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaFormSearchFormDatas(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAFormConstants.YIDA_FORM_SEARCH_FORM_DATAS)
                .addParameter("modifiedFrom", jsonObject.getString("modifiedFrom"))
                .addParameter("formUuid", jsonObject.getString("formUuid"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("dynamicOrder", jsonObject.getString("dynamicOrder"))
                .addParameter("searchFieldJson", jsonObject.getString("searchFieldJson"))
                .addParameter("useOriginValue", jsonObject.getString("useOriginValue"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("createFrom", jsonObject.getString("createFrom"))
                .addParameter("targetFieldJson", jsonObject.getString("targetFieldJson"))
                .addParameter("createTo", jsonObject.getString("createTo"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("originatorId", jsonObject.getString("originatorId"))
                .addParameter("currentPage", String.valueOf(jsonObject.getInteger("currentPage")))
                .addParameter("modifiedTo", jsonObject.getString("modifiedTo"));
        return postClient.post();
    }
```