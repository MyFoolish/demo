---
title: High Performance MySQL
date: 2020-05-20 09:00:00
categories:
- Develop
tag: 
- MySQL
---

# High Performance MySQL

## 序言

在互联网行业，MySQL数据库毫无疑问已经是最常用的数据库。LAMP（Linux＋Apache＋MySQL＋PHP）甚至已经成为专有名词，也是很多中小网站建站的首选技术架构。

**淘宝网**，在2003年非典肆虐期间创立时，选择的就是LAMP架构，当时MySQL的版本还是4.0。但是到了2003年底，由于业务超预期的增长，MySQL 4.0（当时用的还是MyISAM引擎）的很多缺点在高并发大压力下暴露了出来，于是技术上开始改用商业的Oracle数据库。随后几年Oracle加小型机和高端存储的数据库架构支撑了淘宝网业务的爆炸式增长，数据库也从最初的两三个库增长到十几个库，并且每个库的硬件已经逐步升级到顶配，“天花板”很明显地摆在了眼前。于是在2008年，基于PC服务器的MySQL数据库再次成为DBA团队的选择，这时候MySQL的稳定版本已经升级到5.0，并且5.1也已经在开发中，性能和特性相对于2003年的时候已经有了非常大的提升。

淘宝网的数据库架构也逐渐从垂直拆分走向水平拆分，在大规模水平集群的架构设计中，开源的MySQL受到的关注度越来越高，并且一年多来的实践也证明了MySQL（存储引擎主要使用的是InnoDB）在高压力下的可用性。于是从2009年开始，后来颇受外界关注的所谓“去IOE”开始实施，经过三年多的架构改造，到2012年整个淘宝网的核心交易系统已经全部运行在基于PC服务器的MySQL数据库集群中，全部实例数超过2000个。今年的“双11”大促中，MySQL单库经受了最高达6.5万的QPS，某个拥有32个节点的核心集群的总QPS则稳定在86万以上，并且在整个大促（包括之前三年的“双11”大促）期间，数据库未发生过任何影响大促的重大故障。当然，这个结果，也得益于淘宝网整个应用架构的设计，以及这几年来革命性的闪存设备的迅猛发展。