# solr 在线实验环境

## 软件简介

Solr具有高可靠性，可扩展性和容错性，可提供分布式索引，复制和负载平衡查询，自动故障转移和恢复，集中配置等功能。solr提供了许多世界上最大的网站的搜索和导航功能。

所属类别是服务器软件

License： Apache License, Version 2.0

特点：

Solr是一个高性能，采用Java5开发，基于Lucene的全文搜索服务器。同时对其进行了扩展，提供了比Lucene更为丰富的查询语言，同时实现了可配置、可扩展并对查询性能进行了优化，并且提供了一个完善的功能管理界面，是一款非常优秀的全文搜索引擎。
## 软件官网

http://lucene.apache.org/solr/

## Dockerfile 使用方法

### 运行索尔和索引示例数据
运行一个Solr服务器：
```
$ docker run --name my_solr -d -p 8983:8983 -t solr
```
然后使用Web浏览器访问http://localhost:8983/管理控制台（调整Docker主机的主机名）。

要使用Solr，您需要创建一个“核心”，这是数据的索引。例如：
```
$ docker exec -it --user=solr my_solr bin/solr create_core -c gettingstarted
```
在网络界面中，如果您点击“核心管理”，您现在应该看到“入门”核心。

如果要加载容器中包含的一些示例数据：
```
$ docker exec -it --user=solr my_solr bin/post -c gettingstarted example/exampledocs/manufacturers.xml
``` 
在UI中，找到“核心选择器”弹出菜单，选择“入门”核心，然后选择“查询”菜单项。这将为您提供默认搜索*:*，返回所有文档。点击“执行查询”按钮，你应该看到一些带有数据的文档。恭喜！

## 资源链接

- http://lucene.apache.org/solr/
- https://hub.docker.com/_/solr/
