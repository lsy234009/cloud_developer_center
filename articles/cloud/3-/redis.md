# 使用和管理Redis服务

##开发者中心Redis服务简介##

Redis 是一个开源，基于内存的高性能 key-Value 数据库，它支持存储的 value 类型很丰富，包括 string (字符串)、list (链表)、set (集合)、zset (sortedset--有序集合)和 hash（哈希类型）。这些数据类型都支持 push/pop、add/remove 及取交集并集和差集及更丰富的操作，而且这些操作都是原子性的。Redis 对关系型数据库起到很重要的补充作用，并提供丰富的 API 供不同编程语言调用。

开发者中心Redis服务基于Redis 2.8.19版本进行优化和配置，提供简单快速的服务创建和管理功能，为开发者提供便捷实用key-value数据库能力。

服务提供基础的创建、销毁、续期等功能,用户根据自身资源池情况，可以选择不同的配额，设置用户名和密码、服务名称等配置。

##Redis服务管理维护##

第一步：登录云开发者中心网站：https://developer.yonyoucloud.com

第二步：选择左侧菜单，进入中间件服务管理界面

![](/articles/cloud/3-/images/middleware_1.png)

第三步：点击Redis服务磁贴的“创建一个”按钮或者进入管理我的Redis界面，点击“创建服务”按钮,创建自己的Redis服务

![](/articles/cloud/3-/images/redis_2.png)

第四步：输入服务名称、描述、用户名称、密码等，并选择合适的配额，创建Redis服务

![](/articles/cloud/3-/images/redis_3.png)

第五步：进入Redis服务列表管理界面，可以查看服务的状态，刚创建的服务为“部署中”状态

![](/articles/cloud/3-/images/redis_4.png)

第六步：稍等1-2分钟，刷新列表状态，创建的服务更新为运行中状态，服务创建成功，点击此行，查看详细信息

![](/articles/cloud/3-/images/redis_5.png)

第七步：详细信息中展示了Redis服务的内网链接地址、端口号、示例名等信息，开发者可以在开发者中心的网络内使用此链接地址进行应用的配置

第八步：创建的服务默认有效期为半个月，可以点击一次续期延长至一个月，到期前会邮件提醒用户

![](/articles/cloud/3-/images/redis_6.png)

第八步：每个租户默认允许创建3个Redis服务实例，系统会给出提醒信息并跳转至列表管理页

![](/articles/cloud/3-/images/middleware_2.png)