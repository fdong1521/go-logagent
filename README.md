# 采用go语言开发高性能日志采集系统

# 一、项目背景
      日志采集是大数据、数据挖掘的基石，许多企业每天都会产生的大量的日志，收集日志数据供大数据分析平台使用，
      帮助企业挖掘数据潜在的价值，助力企业腾飞。
      目前常用的开源日志收集系统有Flume, Scribe等。
      Flume是Cloudera提供的一个高可用的，高可靠的，分布式的海量日志采集、聚合和传输的系统，目前已经是Apache的一个子项目。
      Scribe是Facebook开源的日志收集系统，它为日志的分布式收集，统一处理提供一个可扩展的，高容错的简单方案。
      Flume是用Java语言开发、Scribe是用c/c++开发
      本项目是用go语言开发
        
# 二、设计思路

# 三、技术选型
      
      开发语言:GoLang
      
      分布式消息队中间件:kafka
      
      分布式配置中间件:etcd
      
      分布式协调中间件:zookeeper
      
      关系型数据库:mysql

# 四、整体架构

![日志集采架构图]("(http://jibao-supplier.oss-cn-shanghai.aliyuncs.com/jibaomall/190103173928_3058062336_cb81f2ad-366c-40ce-8391-2ed1dc2f7c3d..png)

# 五、数据表设计
**1.主机节点表 t_logagent_node**
   主机节点表用于存储需要采集日志的主机信息    
| 字段| 类型 | 描述 |
| :-------------- | :---------------- | :--------------------------- |
| id | int | 主键 |
| key_path | varchar(255) | 关键路径 |
| server_name | varchar(255) | 服务名称 |
| ip |  varchar(16) | 主机内网ip |
| create_time | varchar(32) | 创建时间 |

**2.日志文件配置表 t_logagent_tail**
   日志文件配置表用于存储需要采集日志对象的信息

| 字段| 类型 | 描述 |
| :-------------- | :---------------- | :--------------------------- |
| id | int | 主键 |
| log_path | varchar(255) | 日志路径 |
| topic | varchar(255) | 消息主题 |
| node_id |  varchar(16) | 主机节点 |
| status | varchar(32) | 状态（ 0:停止 1:运行） |
| create_time | varchar(32) | 创建时间 |



# 六、项目部署




# 七、总结
