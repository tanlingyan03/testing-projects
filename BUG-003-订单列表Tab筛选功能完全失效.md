BUG-003: 订单列表Tab筛选功能完全失效
基本信息
项目    内容
缺陷编号    BUG-003
优先级    P0 - 高
严重程度    Blocker
所属模块    订单管理 / OrdersView
发现时间    2026-07-31
测试环境    Chrome 120+ / Windows 11 / 网络正常
测试账号    testuser / ***
复现步骤
1. 用户登录后访问 http://localhost:5173/orders
2. 观察订单列表内容
3. 点击"待付款"Tab
4. 观察列表是否变化
5. 依次点击"待发货""待收货""已完成"Tab

预期结果
切换Tab后应只显示对应状态的订单，列表内容随Tab切换而变化
实际结果
无论切换哪个Tab，都显示全部订单。loadOrders 方法中 getOrderList({}) 始终传空对象，activeTab 的值从未传给API，筛选功能形同虚设
