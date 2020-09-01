# DING API开放

## 接口说明
```java
    /**
     * DING API开放
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GovDingIsvSend(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2536)
## 实现方法
```java
    /**
     * DING API开放
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GovDingIsvSend(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadDingConstants.GOV_DING_ISV_SEND)
                .addParameter("notifyType", jsonObject.getJSONObject("creator").toJSONString())
                .addParameter("notifyType", jsonObject.getString("notifyType"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("textType", jsonObject.getString("textType"))
                .addParameter("body", jsonObject.getString("body"))
                .addParameter("bodyType", jsonObject.getString("bodyType"));
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("receivers"))) {
                jsonObject.getJSONArray("receivers").forEach(receiver -> {
                    postClient.addParameter("receivers", String.valueOf(receiver));
                });
            }
        } catch (Exception e) {
            if(jsonObject.getJSONObject("receivers").toJSONString() != null) {
                postClient.addParameter("receivers", jsonObject.getJSONObject("receivers").toJSONString());
            }
        }
        return postClient.post();
    }
```

