# 工作通知

## 接口说明
```java
    /**
     * 工作通知
     * @param messageWorkNotificationObject messageWorkNotificationObject入参
     * @return java.lang.String
     **/
    String messageWorkNotification(MessageWorkNotificationObject messageWorkNotificationObject);

    /**
     * 工作通知
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String messageWorkNotification(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2356)
## 实现方法
```java
    /**
     * 工作通知
     * @param messageWorkNotificationObject messageWorkNotificationObject入参
     * @return java.lang.String
     **/
    @Override
    public String messageWorkNotification(MessageWorkNotificationObject messageWorkNotificationObject) {
        PostClient postClient = this.newGadPostClient(GadWNMApiConstants.MESSAGE_WORK_NOTIFICATION)
                .addParameter("bizMsgId", messageWorkNotificationObject.getBizMsgId());
        if(StringUtils.isNotEmpty(messageWorkNotificationObject.getTenantId())) {
            postClient.addParameter("tenantId", messageWorkNotificationObject.getTenantId());
        } else {
            throw new GadNullPointerException("tenantId is empty in messageWorkNotification");
        }
        if(messageWorkNotificationObject.getMsg() != null) {
            postClient.addParameter("msg", messageWorkNotificationObject.getMsg().toJSONString());
        } else {
            throw new GadNullPointerException("msg is null in messageWorkNotification");
        }
        if(!CollectionUtils.isEmpty(messageWorkNotificationObject.getOrganizationCodes())) {
            if(messageWorkNotificationObject.getOrganizationCodes().size() <= 20) {
                messageWorkNotificationObject.getOrganizationCodes().forEach(code -> {
                    postClient.addParameter("organizationCodes", code);
                });
            } else {
                throw new GadIndexOutOfBoundsException("The length of the organizationCodes is over 20 in messageWorkNotification");
            }
        }
        if(!CollectionUtils.isEmpty(messageWorkNotificationObject.getReceiverIds())) {
            messageWorkNotificationObject.getOrganizationCodes().forEach(id -> {
                postClient.addParameter("receiverIds", id);
            });
        }
        return postClient.post();
    }

    /**
     * 工作通知
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String messageWorkNotification(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWNMApiConstants.MESSAGE_WORK_NOTIFICATION)
                .addParameter("bizMsgId", jsonObject.getString("bizMsgId"));
        if(StringUtils.isNotEmpty(jsonObject.getString("tenantId"))) {
            postClient.addParameter("tenantId", jsonObject.getString("tenantId"));
        } else {
            throw new GadNullPointerException("tenantId is empty in messageWorkNotification");
        }

        if(StringUtils.isNotEmpty(jsonObject.getString("msg"))) {
            postClient.addParameter("msg", jsonObject.getString("msg"));
        } else {
            throw new GadNullPointerException("msg is empty in messageWorkNotification");
        }

        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("organizationCodes"))) {
                jsonObject.getJSONArray("organizationCodes").forEach(code -> {
                    postClient.addParameter("organizationCodes", String.valueOf(code));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("organizationCodes"))){
                postClient.addParameter("organizationCodes", jsonObject.getString("organizationCodes"));
            }
        }

        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("receiverIds"))) {
                jsonObject.getJSONArray("receiverIds").forEach(id -> {
                    postClient.addParameter("receiverIds", String.valueOf(id));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("receiverIds"))) {
                postClient.addParameter("receiverIds", jsonObject.getString("receiverIds"));
            }
        }
        return postClient.post();
    }
```