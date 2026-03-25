# 仿蜜雪冰城的奶茶点单派送系统
# 技术栈: Springboot、SpringMVC、Mybatis、MySQL、Redis、nginx、POI、OSS、WebSocket 、Spring Task、Spring Cache
# 📋 项目总体逻辑
覆盖点单「管理端+用户端」双端业务，实现从菜品管理到完成订单的闭环流程：

管理端：员工/分类/饮品/套餐管理→订单处理→数据统计与报表导出。商家支撑运营；
用户端（微信小程序）：微信授权登录→商品浏览（饮品/套餐）→购物车操作→地址管理→下单支付→订单查询/取消。满足用户点餐需求；
核心流转（订单处理部分）：商家上架饮品/套餐→用户下单支付→系统实时订单给商家→商家接单/派送→完成订单（超时自动取消）。
# ✨ 核心技术亮点
除了常规的多表CRUD，还包含：

技术栈选型：Spring Boot + Spring MVC + MyBatis 构建架构，MySQL 存储业务数据，Redis 优化存储性能，全栈覆盖主流开发技术；

效率与用优化：AOP + 引用实现 createTime/updateTime 等公共字段自动填充，减少重复代码；

Redis自定义服务器+Spring Cache注解式服务器，降低数据库查询压力；

安全与身份认证：微信小程序登录通过验证码获取openId，实现免注册登录；

JWT生成令牌 + 拦截器鉴权，ThreadLocal存储用户上下文，接口安全；

实时通信与定时任务：WebSocket实现来单提醒、客户催单功能，提升业务响应效率；Spring Task定时处理超时订单，自动更新状态，消耗人工干预；

数据可视化与文件处理：集成ECharts实现营业额、销售额Top10等多维度数据统计；

Apache POI 基于模板导出运营 Excel 报表，配置办公场景；

严谨的服务逻辑设计：关联数据联动（菜品停售同步套餐停售）、合理表关系设计（套餐-菜品多对多），确保流程业务闭环与数据一致性。
# 运行截图
<img width="1915" height="956" alt="00" src="https://github.com/user-attachments/assets/0640e9e4-4a85-41f5-99e4-ff77c7cbde14" />
<img width="1906" height="963" alt="01" src="https://github.com/user-attachments/assets/8833ff44-6fed-4c13-b42b-da3eed8b4ae1" />
<img width="1912" height="959" alt="02" src="https://github.com/user-attachments/assets/c8258219-5e62-49f6-93fb-65801f906196" />
<img width="1902" height="951" alt="03" src="https://github.com/user-attachments/assets/cb637d25-0de1-49c3-acb5-3134701fecf0" />
<img width="1909" height="954" alt="04" src="https://github.com/user-attachments/assets/f2d1f6bd-a545-4ad4-b7b9-ca3128ab6e1d" />
<img width="1909" height="956" alt="05" src="https://github.com/user-attachments/assets/8359266f-df2c-45cc-9965-3fde190d3389" />
<img width="380" height="856" alt="06" src="https://github.com/user-attachments/assets/beda90b5-c219-4c99-9e8e-e6f1d0927068" />
<img width="383" height="860" alt="07" src="https://github.com/user-attachments/assets/aaa2c177-9e38-4177-89ff-29c67d98e38d" />
<img width="379" height="862" alt="08" src="https://github.com/user-attachments/assets/aa079a75-21db-4c34-8d10-e87d82b8176b" />
<img width="383" height="860" alt="07" src="https://github.com/user-attachments/assets/aaa2c177-9e38-4177-89ff-29c67d98e38d" />
<img width="379" height="862" alt="08" src="https://github.com/user-attachments/assets/aa079a75-21db-4c34-8d10-e87d82b8176b" />
