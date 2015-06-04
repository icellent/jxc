#系统名称：南梅公司配送协作系统
#系统概述：系统要求为B/S架构，PHP＋MYSQL搭建
##业务概述：
- 接收合作伙伴的订单需求
- 处理合作伙伴的订单需求
- 管理所有订单，包括订单的状态跟踪与反馈
- 有登录界面，区分不同的角色
##需求描述：
- 合作伙伴通过网页登陆，并提交订单需求。必须实现客户通过xls格式的批量导入的功能
- 合作伙伴导入订单后，我方需收到系统通知，只需在进销存系统通知即可
- 需具备扫码出入库功能（利用扫描枪接电脑扫码）
- 出库时，需要选择订单，将出库的编码与订单关联起来
- 需具备订单管理功能

 1. 具备订单查询功能，能通过号码，姓名或产品类型字段进行条件查询与操作。
 2. 具备反馈功能，能手动填写反馈信息
 3. 订单状态更新工作，可标记订单完成，订单配送中，订单配送失败等状态。并具备日期戳。
 4. 订单管理需具备分类功能，能在管理菜单中选择分类查看订单

- 具备用户权限管理功能，系统内置一个管理员账号，可增加或删除以下两类用户。

 1.一类是我司人员，分配权限为所有，能使用所有功能，权限仅次于管理员。
 2.另一类是合作伙伴，分配权限为访客，只能访问自己上传的订单，查询自己上传订单的状态。
##UI界面
![UI未完成](http://7u2ps7.com1.z0.glb.clouddn.com/vshopjxc.png)

##前置条件
客户访问网站，登录后可进入UI界面
##后置条件
设置登陆时间限制，登录后空闲超时为30分钟
##业务规则
- 合作伙伴账号只能上传订单和查看订单状态，不能执行订单删除与修改，不提供搜索功能
- 订单数据一经上传，无论合作伙伴或我司人员，一律不能删除订单，只能添加反馈内容与标记订单状态
- 只有管理员账号可以操作增删改查

##流程描述
订单上传－－系统通知－－－订单分配－－状态更改－－订单完成（失败）

##数据表字段：
订单编码	订单编号	揽装人号码	销售员编码	客户姓名	号码套餐|宽带产品	证件号码	配送地址(区)	配送详细地址	联系人	联系电话	分销下单备注	受理备注	移动业务号码1	手机型号1	是否同意	第一次回访	第二次回访	第三次	配送号码	配送结果	手机串号	卡串号	配送人/日期	发单日期
