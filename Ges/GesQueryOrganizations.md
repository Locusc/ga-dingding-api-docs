# 获取签章机构列表

## 接口说明
```java
    /**
     * 获取签章机构列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String gesQueryOrganizations(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2560)
## 实现方法
```java
    /**
     * 获取签章机构列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String gesQueryOrganizations(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadGESConstants.GES_QUERY_ORGANIZATIONS)
                .addParameter("organizationName", jsonObject.getString("organizationName"))
                .addParameter("essp", jsonObject.getString("essp"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("currentPage", String.valueOf(jsonObject.getInteger("currentPage")));
        return postClient.post();
    }
```