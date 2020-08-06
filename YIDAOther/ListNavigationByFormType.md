# 获取应用下所有表单页面的列表

## 接口说明
```java
    /**
     * 获取应用下所有表单页面的列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaAppListNavigationByFormType(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2598)
## 实现方法
```java
    /**
     * 获取应用下所有表单页面的列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaAppListNavigationByFormType(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAOtherConstants.YIDA_APP_LIST_NAVIGATION_BY_FORM_TYPE)
                .addParameter("formType", jsonObject.getString("formType"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```