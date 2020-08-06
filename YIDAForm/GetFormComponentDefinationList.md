# 获取表单定义

## 接口说明
```java
    /**
     * 获取表单定义
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaFormDesignGetFormComponentDefinationList(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2593)
## 实现方法
```java
    /**
     * 获取表单定义
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaFormDesignGetFormComponentDefinationList(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAFormConstants.YIDA_FORM_DESIGN_GET_FORM_COMPONENT_DEFINATION_LIST)
                .addParameter("formUuid", jsonObject.getString("formUuid"))
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("version", String.valueOf(jsonObject.getLong("version")))
                .addParameter("userId", jsonObject.getString("userId"));
        return postClient.post();
    }
```