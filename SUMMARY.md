# Summary

## 前序
* [简介](README.md)
* [注意事项](Preorder/attention.md)

## 方法和接口说明
* [DING](Ding/README.md)
    * [DING API开放](Ding/Ding_Api_Open.md)
* [评论](Comments/README.md)
    * [根据条件删除点赞](Comments/BipLikeDeleteByConditions.md)
    * [根据id查询点赞](Comments/BipLikeGet.md)
    * [根据条件查询点赞数量](Comments/BipLikeCountLike.md)
    * [根据不同条件查询点赞,并限制返回数量,根据主题id分类](Comments/BipLikeLimitQueryGroupBySubjectId.md)
    * [根据不同条件查询点赞](Comments/BipLikeQuery.md)
    * [更新点赞](Comments/BipLikeUpdate.md)
    * [点赞](Comments/BipLikeAdd.md)
    * [根据条件删除评论](Comments/BipCommentDeleteByConditions.md)
    * [根据评论id查询评论](Comments/BipCommentGet.md)
    * [根据条件查询评论数量](Comments/BipCommentCountComments.md)
    * [根据不同条件查询评论/回复评论,并限制返回数量,根据主题id分组返回](Comments/BipCommentLimitQueryGroupBySubjectId.md)
    * [根据不同条件查询评论/回复评论](Comments/BipCommentQuery.md)
    * [更新评论/更新评论回复](Comments/BipCommentUpdate.md)
    * [评论/评论回复](Comments/BipCommentAdd.md)
* [电子签章](Ges/README.md)
    * [获取签章机构列表](Ges/GesQueryOrganizations.md)
    * [获取签章管理员列表](Ges/GesQuerySealKeepers.md)
    * [获取印章列表](Ges/GesQuerySeals.md)
    * [发送签章验证码](Ges/GesStampSendVerifyCode.md)
    * [验证签章验证码](Ges/GesStampCheckVerifyCode.md)
    * [签署盖章](Ges/GesStampSign.md)
* [人脸识别](FaceRecognition/README.md)
    * [图片压缩,按照宽高压缩](FaceRecognition/BipFaceCompressForBorder.md)
    * [图片压缩,按照比例,精度压缩](FaceRecognition/BipFaceCompressForScale.md)
    * [压缩图片,根据需要的字节大小,精度压缩](FaceRecognition/BipFaceCompressForSize.md)
    * [人脸属性识别](FaceRecognition/BipFaceAttribute.md)
    * [人脸比对（上传两张图片比对）](FaceRecognition/BipFaceVerifyWithOriginalImg.md)
    * [人脸比对(服务端事先录入原图)](FaceRecognition/BipFaceVerify.md)
    * [人脸检测](FaceRecognition/BipFaceDetect.md)
* [水印](WaterMark/README.md)
    * [制作水印](WaterMark/BipWaterMarkDoWaterMark.md)
    * [添加水印模板](WaterMark/BipWaterMarkTemplateSave.md)
    * [修改水印模板](WaterMark/BipWaterMarkTemplateEdit.md)
    * [水印模板分页查询](WaterMark/BipWaterMarkTemplatePageQuery.md)
    * [删除水印模板](WaterMark/BipWaterMarkTemplateDel.md)
    * [获取云端保存的水印文件（分页）](WaterMark/BipWaterMarkPage.md)
    * [移动端获取水印模板](WaterMark/BipWaterMarkTemplateQuery.md)
* [宜搭其他](YIDAOther/README.md)
    * [获取应用下所有表单页面的列表](YIDAOther/ListNavigationByFormType.md)
    * [宜搭附件地址转临时免登地址](YIDAOther/GetOpenUrl.md)
    * [增加评论](YIDAOther/RemarkSave.md)
* [宜搭任务中心](YIDATaskCenter/README.md)
    * [查询已完成任务](YIDATaskCenter/GetDoneTasksInCorp.md)
    * [查询待办任务](YIDATaskCenter/GetTodoTasksInCorp.md)
    * [已提交任务](YIDATaskCenter/getMySubmmitInCorp.md)
* [宜搭流程](YIDAProcess/README.md)
    * [根据搜索条件获取实例详情列表](YIDAProcess/GetInstances.md)
    * [获取流程设计节点上的按钮列表](YIDAProcess/GetActivityButtonVOs.md)
    * [流程实例更新](YIDAProcess/UpdateInstance.md)
    * [执行虚拟节点任务](YIDAProcess/ExecutePlatformTask.md)
    * [获取审批记录](YIDAProcess/GetOperationRecords.md)
    * [执行单个任务接口](YIDAProcess/ExecuteTask.md)
    * [终止流程实例](YIDAProcess/TerminateInstance.md)
    * [删除流程实例](YIDAProcess/DeleteInstance.md)
    * [根据实例ID获取流程实例详情](YIDAProcess/GetInstanceById.md)
    * [搜索流程实例ID](YIDAProcess/GetInstanceIds.md)
    * [流程发起](YIDAProcess/StartInstance.md)
* [宜搭表单](YIDAForm/README.md)
    * [获取表单定义](YIDAForm/GetFormComponentDefinationList.md)
    * [根据条件搜索单据实例详情列表](YIDAForm/SearchFormDatas.md)
    * [根据条件搜索单据实例ID列表](YIDAForm/SearchFormDataIds.md)
    * [根据单据实例ID查询单据实例详情](YIDAForm/GetFormDataById.md)
    * [删除单据实例](YIDAForm/DeleteFormData.md)
    * [更新单据中指定组件值](YIDAForm/UpdateFormData.md)
    * [新增单据实例](YIDAForm/SaveFormData.md)
* [轨迹服务](TrackService/README.md)
    * [外部服务查询用户轨迹](TrackService/GBS_TQ_QUTBI.md)
    * [外部服务停止轨迹上报](TrackService/GBS_T_StopTCBI.md)
    * [外部服务开启轨迹采集](TrackService/GBS_T_StartTCBI.md)
    * [isv或外部服务生成轨迹id](TrackService/GBS_T_GTIBI.md)
    * [获取轨迹推送失败消息](TrackService/BIP_R_FT.md)
    * [应用注销轨迹推送](TrackService/BIP_R_C.md)
    * [获取轨迹推送注册](TrackService/BIP_R_GE.md)
    * [应用更新轨迹推送事件数据](TrackService/BIP_R_UE.md)
    * [轨迹推送注册](TrackService/BIP_R_RA.md)
    * [开启轨迹采集](TrackService/GbsTraceStartTraceCollect.md)
    * [校验轨迹id](TrackService/GbsTraceCheckTraceId.md)
    * [根据位置范围查询用户](TrackService/GbsTraceQueryUserByGeoScope.md)
* [消息](Message/README.md)
    * [创建群会话](Message/Chat_Creat.md)
    * [发送消息](Message/Chat_SendMsg.md)
    * [获取群成员](Message/Chat_Group_Get_Users.md)
    * [获取消息已读人数](Message/Chat_Group_Message_Read_Users.md)
    * [更新群会话](Message/Chat_Group_Update.md)
* [业务事件回调](EventCallBack/README.md)
    * [移除失败回调](EventCallBack/Remove_CB_Failed.md)
    * [重试失败回调](EventCallBack/Retry_CB_Failed.md)
    * [查询回调失败信息](EventCallBack/Query_CB_Failed.md)
    * [删除事件回调的定义信息](EventCallBack/Delete_E_CB_Define.md)
    * [更新事件回调的定义信息](EventCallBack/Update_E_CB_Define.md)
    * [查询定义的事件列表](EventCallBack/Query_CB_Define.md)
    * [注册消息回调](EventCallBack/Register_E_CB.md)
    * [注册消息回调(支持加密,签名)](EventCallBack/V2_Register_E_CB.md)
* [JSAPI鉴权](JSAPI/README.md)
    * [get_jsapi_token.json](JSAPI/Get_Jsapi_Token.md)
* [文件存储](FileStorage/README.md)
    * [媒体文件下载](FileStorage/MediaDownload.md)
* [日程](Schedule/README.md)
    * [取消日历事件](Schedule/CancelCalendar.md)
    * [创建日历事件](Schedule/CreateCalendar.md)
    * [获取APP设置可见的用户Id](Schedule/AppQueryAppVisibleList.md)
    * [从可见用户列表中删除指定用户](Schedule/AppRemoveUserFromAppVisibleList.md)
    * [设置APP的用户可见性](Schedule/AppAddUserToAppVisibleList.md)
    * [获取用户可用的app](Schedule/AppUserVisibleApps.md)
* [待办](Todo/README.md)
    * [取消实例接口](Todo/PackageCancel.md)
    * [关闭实例接口](Todo/PackageClose.md)
    * [取消待办接口](Todo/TaskCancel.md)
    * [完成待办接口](Todo/TaskFinish.md)
    * [创建待办接口V2](Todo/TaskCreate.md)
* [工作通知消息](Notification/README.md)
    * [工作通知](Notification/WorkNotification.md)
    * [发送工作台红点](Notification/SendPortalNotification.md)
    * [清除工作台红点](Notification/ClearPortalNotification.md)
    * [查询工作台红点](Notification/QueryPortalNotification.md)
* [获取通讯录部门信息](AddressBookDeptInfo/README.md)
    * [移动组织](AddressBookDeptInfo/MoveGovOrganization.md)
    * [删除组织](AddressBookDeptInfo/DeleteGovOrganization.md)
    * [更新组织](AddressBookDeptInfo/UpdateGovOrganization.md)
    * [创建组织](AddressBookDeptInfo/CreateGovOrganization.md)
    * [根据组织Code列表查询详情](AddressBookDeptInfo/ListOrganizationsByCodes.md)
    * [根据组织查询组织汇报线](AddressBookDeptInfo/GetOrganizationLine.md)
    * [分页查询组织下的员工Code](AddressBookDeptInfo/PageOrganizationEmployeeCodes.md)
    * [根据组织code查询详情](AddressBookDeptInfo/GetOrganizationByCode.md)
    * [分页获取下一级组织Code列表](AddressBookDeptInfo/PageSubOrganizationCodes.md)
    * [获取租户根组织](AddressBookDeptInfo/GetRootOrganization.md)
    * [分页获取下一级行政区划列表](AddressBookDeptInfo/PageSubGovDivisions.md)
    * [根据行政区划查询行政区划线](AddressBookDeptInfo/GetDivisionLine.md)
    * [根据行政区划Code列表查询](AddressBookDeptInfo/ListDivisionsByCodes.md)
    * [分页获取下一级条线列表](AddressBookDeptInfo/PageSubGovBusinessStrips.md)
    * [根据条线查询条线线](AddressBookDeptInfo/GetGovBusinessStripLine.md)
    * [根据条线Code列表查询](AddressBookDeptInfo/ListGovBusinessStripsByCodes.md)
    * [组织ID转换接口](AddressBookDeptInfo/ZzdDeptGetDepMapByType.md)
    * [根据组织code查询组织下的员工人数](AddressBookDeptInfo/DeptGetOrganizationEmployeeCount.md)
* [获取通讯录用户信息](AddressBookUserInfo/README.md)
    * [冻结和解冻账号](AddressBookUserInfo/UpdateGovAccountStatus.md)
    * [根据员工Code获取员工标签Code列表](AddressBookUserInfo/ListEmployeeTags.md)
    * [删除员工的任职](AddressBookUserInfo/DeleteGovEmployeePosition.md)
    * [更新员工的任职](AddressBookUserInfo/UpdateGovEmployeePosition.md)
    * [删除员工](AddressBookUserInfo/DeleteGovEmployee.md)
    * [失效员工](AddressBookUserInfo/DeactivateGovEmployee.md)
    * [修改员工](AddressBookUserInfo/UpdateGovEmployee.md)
    * [创建员工的任职](AddressBookUserInfo/CreateGovEmployeePosition.md)
    * [新增员工](AddressBookUserInfo/CreateGovEmployee.md)
    * [根据组织Code,员工Code列表,批量获取员工在该组织的任职](AddressBookUserInfo/ListOrgEmployeePositionsByCodes.md)
    * [根据员工Code列表查询详情](AddressBookUserInfo/ListEmployeesByCodes.md)
    * [根据员工Code获取员工的任职](AddressBookUserInfo/ListEmployeePositionsByEmployeeCode.md)
    * [根据员工Code查询详情](AddressBookUserInfo/GetEmployeeByCode.md)
    * [通过员工Code列表获取员工账号ID](AddressBookUserInfo/ListEmployeeAccountIds.md)
    * [批量根据accountId、tenantId、organizationCode查询这个账号是否在这个租户的这些组织内](AddressBookUserInfo/ListAccountOrgByIdAndCodes.md)
    * [人员返聘](AddressBookUserInfo/RehiredGovEmployee.md)
    * [根据组织code和批量员工Code获取员工的邮箱信息](AddressBookUserInfo/ListGovOrgEmployeeEmailByCodes.md)
    * [批量通过账号Id列表获取人员Code](AddressBookUserInfo/ListGovEmployeeCodesByAccountIds.md)
    * [查询映射关系通过数梦Id](AddressBookUserInfo/GetEmpCodeByDtUserId.md)
    * [查询映射关系通过钉钉id](AddressBookUserInfo/GetEmpCodeByDingUserId.md)
    * [根据手机号码获取人员编码](AddressBookUserInfo/GetByMobile.md)
    * [移动任职](AddressBookUserInfo/GetMoveEmpPosition.md)
    * [人员排序](AddressBookUserInfo/ReorderEmpPositionsByCodes.md)
    * [获取通讯录权限范围v2](AddressBookUserInfo/AuthScopesV2.md)
    * [查询角色授权详情信息](AddressBookUserInfo/GetGrantRoleDataDetail.md)
    * [查询组织下人员详情](AddressBookUserInfo/PageOrganizationEmployeePositions.md)
    * [批量新增人员标签](AddressBookUserInfo/BatchCreateEmployeeTag.md)
    * [批量删除人员标签](AddressBookUserInfo/BatchDeleteEmployeeTag.md)
    * [根据标签code获取人员信息列表](AddressBookUserInfo/PageEmployeesByTagCode.md)
    * [启用/停用标签](AddressBookUserInfo/UpdateTagStatus.md)
    * [获取标签列表](AddressBookUserInfo/PageTags.md)
    * [删除标签](AddressBookUserInfo/DeleteTag.md)
    * [删除标签组](AddressBookUserInfo/DeleteTagGroup.md)
    * [根据标签组code获取标签列表](AddressBookUserInfo/PagTagsByGroupCode.md)
    * [获取标签详情](AddressBookUserInfo/GetTagDetail.md)
    * [根据标签code列表获取标签详情](AddressBookUserInfo/GetTagsDetailByCodes.md)
    * [创建标签组](AddressBookUserInfo/CreateTagGroup.md)
    * [添加标签](AddressBookUserInfo/AddTag.md)
    * [获取所有标签组](AddressBookUserInfo/PageTagGroups.md)
    * [根据标签组code获取人员信息列表](AddressBookUserInfo/PageEmployeesByTagGroupCode.md)
    * [获取通讯录权限范围](AddressBookUserInfo/GetAuthScopes.md)
* [应用管理后台免登](AMBLogin/README.md)
    * [服务端通过临时授权码获取授权用户的个人信息](AMBLogin/GetUserInfoByCode.md)
* [企业内应用免登](NotLogin/README.md)
    * [根据authCode获取登录token](NotLogin/DingTalk_App_Token.md)
    * [根据authCode换取用户信息](NotLogin/DingTalk_App_User.md)
    * [获取应用access_token](NotLogin/Get_Token.md)

## 最后
* [致谢](TheEnd/ThanksFor.md)

