# 根据手机号码获取人员编码

## 接口说明
```java
    /**
     * 根据手机号码获取人员编码
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeGetByMobile(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2494)
## 实现方法
```java
    /**
     * 根据手机号码获取人员编码
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeGetByMobile(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_GET_BY_MOBILE)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("areaCode", jsonObject.getString("areaCode"))
                .addParameter("namespace", jsonObject.getString("namespace"))
                .addParameter("mobile", jsonObject.getString("mobile"));
        return postClient.post();
    }
```