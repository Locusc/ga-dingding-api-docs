# 查询映射关系通过钉钉id

## 接口说明
```java
    /**
     * 查询映射关系通过钉钉id
     * @param dingUserId 钉钉id
     * @return java.lang.String
     **/
    String employeeGetEmpCodeByDingUserId(String dingUserId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2503)
## 实现方法
```java
    /**
     * 查询映射关系通过钉钉id
     * @param dingUserId 钉钉id
     * @return java.lang.String
     **/
    @Override
    public String employeeGetEmpCodeByDingUserId(String dingUserId) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_GET_EMP_CODE_BY_DING_USER_ID)
                .addParameter("dingUserId", dingUserId);
        return postClient.post();
    }
```