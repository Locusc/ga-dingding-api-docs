# 查询映射关系通过数梦Id

## 接口说明
```java
    /**
     * 查询映射关系通过数梦Id
     * @param dtUserId 数梦用户id
     * @return java.lang.String
     **/
    String employeeGetEmpCodeByDtUserId(String dtUserId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2504)
## 实现方法
```java
    /**
     * 查询映射关系通过数梦Id
     * @param dtUserId 数梦用户id
     * @return java.lang.String
     **/
    @Override
    public String employeeGetEmpCodeByDtUserId(String dtUserId) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_GET_EMP_CODE_BY_DT_USER_ID)
                .addParameter("dtUserId", dtUserId);
        return postClient.post();
    }
```