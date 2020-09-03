# 媒体文件下载

## 接口说明
```java
    /**
     * 媒体文件下载
     * @param accessToken 校验权限的appToken
     * @param mediaId 上传成功后返回的mediaId
     * @return java.lang.String
     **/
    String mediaDownload(String accessToken, String mediaId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2530)
## 实现方法
```java
    /**
     * 媒体文件下载
     * @param accessToken 校验权限的appToken
     * @param mediaId 上传成功后返回的mediaId
     * @return java.lang.String
     **/
    @Override
    public String mediaDownload(String accessToken, String mediaId) {
        PostClient postClient = this.newGadPostClient(GadFileStorageConstants.MEDIA_DOWNLOAD)
                .addParameter("access_token", accessToken)
                .addParameter("media_id", mediaId);
        return postClient.post();
    }
```