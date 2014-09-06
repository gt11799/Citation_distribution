Citation_distribution
=====================
文档的引用可以看作一个有向图，data-cite.txt存放着文档引用的数据，其中文档以数字表示，每一行的第一个是该文档，其他为该文档引用的文档。
程序读取文档，转换为字典，然后计算出入度（in-degree）的分布，并绘图。
用到了以前提交的graph-compute.py中图的基础处理的几个模块。（graph-compute）
