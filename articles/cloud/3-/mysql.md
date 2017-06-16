# 使用和管理MySQL服务

## 开发者中心MySQL服务简介 ##

MySQL 是一种开放源代码的关系型数据库管理系统（RDBMS），MySQL 数据库系统使用最常用的数据库管理语言--结构化查询语言（SQL）进行数据库管理。 MySQL由于其性能高、成本低、可靠性好，已经成为最流行的开源数据库，被广泛地应用在 Internet 上的中小型网站中。

开发者中心MySQL服务集成MySQL服务和开源数据库管理服务phpMyAdmin于一体，并提供基础的创建、销毁、续期等功能,用户根据自身资源池情况，可以选择不同的配额，设置用户名和密码、服务名称等配置。

利用MySQL的可视化管理界面和关系型数据库的能力，结合中间件服务的其他功能，开发者可以快速开发基于数据库的互联网应用。

## MySQL服务管理维护 ##

第一步：登录云开发者中心网站：https://developer.yonyoucloud.com

第二步：选择左侧菜单，进入中间件服务管理界面

![](/articles/cloud/3-/images/middleware_1.png)

第三步：点击MySQL服务磁贴的“创建一个”按钮或者进入管理我的MySQL界面，点击“创建服务”按钮,创建自己的MySQL服务

![](/articles/cloud/3-/images/mysql_2.png)

第四步：输入服务名称、描述、用户名称、密码等，并选择合适的配额，创建MySQL服务

![](/articles/cloud/3-/images/mysql_3.png)

第五步：进入MySQL服务列表管理界面，可以查看服务的状态，刚创建的服务为“部署中”状态

![](/articles/cloud/3-/images/mysql_4.png)

第六步：稍等1-2分钟，刷新列表状态，创建的服务更新为运行中状态，服务创建成功，点击此行，查看详细信息

![](/articles/cloud/3-/images/mysql_5.png)

第七步：详细信息中展示了MySQL服务的外网管理界面地址、内网链接地址、端口号等信息，开发者可以在开发者中心的网络内使用此链接地址进行应用的配置

第八步：创建的服务默认有效期为半个月，可以点击一次续期延长至一个月，到期前会邮件提醒用户

第九步：打开外网管理地址链接，进入phpMyAdmin登录界面
![](/articles/cloud/3-/images/mysql_6.png)

第十步：输入用户名和密码，进入phpMyAdmin管理界面，用户可以在此创建库和表

![](/articles/cloud/3-/images/mysql_7.png)

第十一步：每个租户默认允许创建3个Redis服务实例，系统会给出提醒信息并跳转至列表管理页

![](/articles/cloud/3-/images/middleware_2.png)