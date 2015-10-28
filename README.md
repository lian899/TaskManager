## .net 简单任务调度平台 ##

用于.net dll,exe的任务的挂载，任务的隔离，调度执行，访问权限控制，监控，管理，日志，错误预警，性能分析等。

1) 平台基于quartz.net进行任务调度功能开发，采用C#代码编写, 支持corn表达式和第三方自定义的corn表达式扩展。

2) 架构以插件形式开发，具有良好的功能扩展性，稳定性，简单性，便于第三方开发人员进一步进行功能扩展。

3) 支持多节点集群，便于集群服务器的资源有效分配，任务的相互隔离。

4) 支持邮件形式的错误预警，便于运维及时处理任务异常等。


（项目允许用于第三方公司进行二次开发且在公司内部使用，但禁止以盈利为目的进行商业行为）



-- 车江毅 2015-06-17


## 未来构想： ##

- 1) 任务故障转移: 检测到任务持续故障n次或者故障频率，判定进行异地节点/节点集群内的任务启动，可支持n次故障恢复。
- 2）任务负载均衡: 多个任务并行执行，用于高资源负载任务的多节点运行。
- 3）任务拆分: 一个父级任务可以创建多个子任务，并对任务进行管理，调度，故障恢复，预警等。


## Dyd.BaseService.TaskManager源码部署须知： ##
- 1、删除各个项目中Newtonsoft.Json.dll的引用
- 2、检查各项目中XXF.dll的引用，确保引用了“引用”文件夹中的XXF.dll
- 3、执行,建模脚本.txt中的sql server脚本语句
- 4、【Dyd.BaseService.TaskManager.Web】 任务管理后台，部署此站点，修改web.config数据库的字符串连接
- 5、修改登录代码和用户权限（看源码），不用源码内部通过crm登录
- 6、【Dyd.BaseService.TaskManager.MonitorTasks】 监控任务，此任务需要重新生成，打包此此文件（原有的打包文件可以直接删除）
- 7、【Dyd.BaseService.TaskManager.WinService】 进行服务安装，修改安装包的实际路径
- 8、管理后台，可以正常访问后，请参照 “任务调度平台安装->任务调度平台部署流程(示例).xls”,来新建任务，调通任务可以正常进行，则为成功
-    (感谢俞忠亮同学整理)
## 开源相关群: .net 开源基础服务 238543768 ##
(大家都有本职工作，也许不能及时响应和跟踪解决问题，请谅解。)

