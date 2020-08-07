# 获取签章管理员列表

## 接口说明
```java
    /**
     * 获取签章管理员列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String gesQuerySealKeepers(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2559)
## 实现方法
```java
    /**
     * 获取签章管理员列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String gesQuerySealKeepers(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadGESConstants.GES_QUERY_SEAL_KEEPERS)
                .addParameter("organizationId", jsonObject.getString("organizationId"))
                .addParameter("essp", jsonObject.getString("essp"));
        return postClient.post();
    }
```