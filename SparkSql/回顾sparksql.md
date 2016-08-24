##### 回顾SparkSQL
* 处理的数据90%来源于Hive表（Hive数据仓库）
* 过程
	* Hadoop -> Hive -> SparkSQL
* 建议：
	* 编写项目时，最后写上使用SparkSQL在调研，在运行，尝试
* 程序入口
	* SQLContext & HiveContext
	* RDD、DataFrame、Dataset
	* 外部数据源（json、parquet、jdbc、table）
* 与Hive的集成
	* sqlContext.sql("select * from emp").show
* ThriftServer
	* 启动一个SparkApplication，多个客户连接
	* beeline
	* jdbc
* 存储分析结果
	* dataframe.write(json、jdbc、table、text)
	
#### Spark如何与HBase进行集成？？
* spark 如何与HBase进行交互？
	1. 读数据
	2. 写数据
* SparkCore
	* read：hbase ->table-> RDD
	* write -> Cell
* SparkSQL
	* SparkSQL -> Hive -> HBase
	* Hive与HBase集成时，需要将HBase Client相关Jar包放入
* SparkSQL External Data Source 
