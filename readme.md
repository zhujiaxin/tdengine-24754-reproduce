运行一次ParameterBindingDemo会创建test_parabind.stable2超级表，自动使用last_row的缓存方式

后续继续运行会自动跳过创建数据库和超级表
运行多次此sql
`select last_row(*),tbname from test_parabind.stable2 group by tbname order by tbname`
会发现时间不同但是f1列结果相同，可以一边运行一边进行查询，会发现f2变化，但是f1不变化。

tdengine version: 3.2.2.0 -docker

tdengine client:3.2.2.0-windows
其他都在pom中。