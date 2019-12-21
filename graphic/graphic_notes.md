### <font color="blue">完全二分图</font>：待填坑[TODO]
### <font color="blue">平面图</font>：可以画在平面上并且使得不同的边可以互不交叠的图。
* 完全图$K_5$和完全二分图$K_{3,3}$(汤玛森图)是最"小"的非平面图。
<table align="center">
<tr>
    <td colspan="2" align="center"> 几个例子 </td>
</tr>
<tr>
    <td align="center">平面图</td>
    <td align="center">非平面图</td>
</tr>
<tr>
    <td align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f9/Butterfly_graph.svg/227px-Butterfly_graph.svg.png">
    <center>蝶行图，平面图的一种</center>
    </td>
    <td align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Complete_graph_K5.svg/612px-Complete_graph_K5.svg.png" width="200" height="200">
    <center>K5不是平面图</center>
    </td>
</tr>
<tr>
    <td align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/6n-graf.svg/333px-6n-graf.svg.png" width="200">
    <center>一个平面图</center>
    </td>
    <td>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Complete_bipartite_graph_K3%2C3.svg/791px-Complete_bipartite_graph_K3%2C3.svg.png" width="200">
    <center>K3,3(汤玛森图)不是平面图</center>
    </td>
</tr>
<tr>
    <td colspan="2" align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Graf_K4_v_rovin%C4%9B.svg/461px-Graf_K4_v_rovin%C4%9B.svg.png">
    <center>K4似乎不是平面图，但实际上只要把K4的一条对角线移出去就可以了</center>
    </td>
</tr>
</table>

### <font color="blue">正则图</font>：每个顶点都有相同数目的邻居的图，即每个顶点的度相同。若每个顶点的度均为$k$，称为$k$-正则图
### <font color="blue">完全图</font>：是每对顶点之间都恰连有一条边的简单图。n个端点的完全图有n个端点及$n(n-1)/2$条边，用$K_n$表示。他是$(n-1)$-正则图。所有完全图都是它本身的团。
<div align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Complete_graph_K7.svg/611px-Complete_graph_K7.svg.png" width="300" height="300" alt="完全图" align=center /></div>
<center>完全图</center>

### <font color="blue">团</font>：在一个无向图中，满足两两之间有边连接的<font color="red">顶点的集合</font>，被称为该无向图的团。  
* **定义**：在无向图G = (V,E)中，如果顶点集C是顶点集V的子集(C${\subseteq}$V)，而且任意两个C中的顶点都有边连接，那么顶点集C被称为图G的**团**。另一种等价的说法是，由C诱导的子图是**完全图**
* **极大团**：指增加任一顶点都不再符合团的定义的团，即极大团不能被任何一个更大的团所包含。
* **最大团**：是一个图中顶点数最多的团。图G的团数$\omega(G)$是指G中最大团的顶点数。
* **边团覆盖数**：是指覆盖G中所有的边所需要的最少的团的数目，称为图G的边团覆盖数。
* **二分维数**：是指覆盖G中所有边所需要的最少的二分团的数目。
* **二分团**：就是完全二分图。
### <font color="blue">顶点(或节点)</font>：是构成图的基本单位。
### <font color="blue">顶点的类型</font>:
**顶点的度**：指的是在图中与这个顶点相连的边的数量。  
**出度**：在有向图中表示从该节点指向其他节点的边的数量，表示为${\delta}^+(v)$。  
**入度**：在有向图中表示从其他节点指向该节点的边的数量，表示为${\delta}^-(v)$。
* **孤立顶点**：度为0的顶点;
* **叶子顶点(亦称终端顶点)**：是一个度为1的顶点;
* **源点**：是一个入度为0的点;
* **汇点**：是一个出度为0的点;
* **简单点**：是其邻接点形成一个团的点。
* **完全点**：是一个连接了其余顶点的顶点。
* **分割点**：是删去后会导致图不再连通的顶点。
* **顶点分割集**：是分割点的集合。
* **K-顶点连通图**：是指一个删去少于K个点总会使剩余图保持连通的图。
* **独立集**：是一个没有任意一对顶点相连的集合，
* **顶点传递图**：如果图的对称性能使得任何顶点映射到任何其他顶点，则该图是顶点传递图。
### <font color="blue">覆盖</font>：
* **顶点覆盖**：图G的顶点覆盖是一个顶点的集合V，使得G中的每一条边都接触V中的至少一个顶点。我们称集合V覆盖了G的边。
* **最小顶点覆盖**：用最少的顶点来覆盖所有的边。
* **顶点覆盖数$\tau$**：是最小顶点覆盖的大小。
* **边覆盖**：是一个边集合E，使得G中的没一个顶点都接触E中的至少一条边。
  * **PS**：如果只说覆盖，通常是指顶点覆盖，而不是边覆盖。
### <font color="blue">边</font>：在<font color="red">无向图</font>中边为顶点的无序对，在<font color="red">有向图</font>中边为定点的有序对
### <font color="blue">端点</font>：两个被一条边所连接的顶点称做该边的端点。
### <font color="blue">图的定义</font>：
#### 定义方式：
* **二元组定义**：一张图$G$是一个二元组$(V,E)$，其中$V$称为顶点集，$E$称为边集。他们亦可写成$V(G)$和$E(G)$。$E$的元素是一个二元数组对，用$(x,y)$表示，其中$x,y\in V$。
* **三元组定义**：一张图$G$是一个三元组$(V,E,I)$，其中$V$称为顶集，$E$称为边集，$E$与$V$不相交;$I$称为关联函数，$I$将$E$中的没一个元素映射到$V\times V$。如果$I(e)=(u,v)(e\in E, u,v\in V)$那么称边$e$连接顶点$u$,$v$，而$u$,$v$称作$e$的端点，$u$,$v$此时关于$e$相邻。同时，若两条边$i$,$j$有一个公共顶点$u$，则称$i$,$j$关于$u$相邻。
#### 分类：
* **有向图**：如果给每条边规定一个方向，那么得到的图称为有向图，其边也称为有向边。与每一个节点相关联的边有出边和入边之分，而与一个有向边关联的两个点也有始点和终点之分。
* **无向图**：边没有方向的图称为无向图。
* **简单图**：一个图如果
  * 1.没有两条边，他们所关联的两个点都相同(在有向图中，没有两条边的起点终点都分别相同);
  * 2.每条边所关联的是两个不同的顶点。  
则称为简单图。
* **多重图**：若允许两结点间的边数多于一条，又允许顶点通过同一条边和自己关联，则称为多重图。它只能用“三元组的定义”。
#### 基本术语：
* **阶**：图$G$中顶集$V$的大小称作图$G$的阶。
* **子图**：图$G'$称作图$G$的子图如果$V(G')\subseteq V(G)$以及$E(G')\subseteq E(G)$。
* **生成子图**：指满足条件$V(G')\subseteq V(G)$的$G$的子图$G'$。
* **[邻接矩阵](https://zh.wikipedia.org/wiki/%E9%84%B0%E6%8E%A5%E7%9F%A9%E9%99%A3)**：
* **自环**：若一条边的两个顶点相同，则此边称为自环。
* **路径**：从顶点$u$到顶点$v$的一条路径是指一个序列$v_0,e_1,v_1,e_2,v_2,...e_k,v_k$，$e_i$的起点终点为$v_{i-1}$及$v_i$;$k$称作路径的长度;$v_0=u$，成为路径的起点;$v_k=v$，称为路径的终点。如果$u=v$，称该路径是**闭**的，反之则称为**开**的;如果$v_1,...,v_k$两两不等，则称之为简单路径。
* **行迹**：如果路径$P(u,v)$中边各不相同，则该路径称为$u$到$v$的一条行迹。
* **轨道**：即简单路径。
* **回路**：闭的行迹。
* **圈**：闭的轨道。
* **距离**:从顶点$u$出发到顶点$v$的最短路径若存在，则此路径的长度成为从$u$到$v$的距离。若从$u$到$v$根本不存在路径，则记该距离为($\infty$)。
* **[距离矩阵](https://zh.wikipedia.org/wiki/%E8%B7%9D%E9%9B%A2%E7%9F%A9%E9%99%A3)**：
* **桥**：若去掉一条边，便会使得整个图不连通，该边称为桥。
### <font color="blue">导出子图</font>：一个图的导出子图是指，由该图的顶点集合的子集和该图中两端均在该子集中的所有<font color="red">边的集合</font>组成的图。