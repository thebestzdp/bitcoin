# 区块链相关知识：

## 概要：
###定义: 

[**概念**](https://bitsonblocks.net/2015/09/09/a-gentle-introduction-to-blockchain-technology/): 

	火币网关于比特币相关概念定义 1
	区块链是比特币的核心与基础架构，是一个去中心化的账本系统（安全可信）。
	
	Multichain的概念定义 2
	Blockchains are great when multiple parties need to 
	read the same information but for whatever reason 
	there can’t be or shouldn’t be any specific individual 
	party in control of that data.
	
	狭义概念定义 3
	从技术层面来看，区块链是一个基于共识机制、去中心化的公开数据库。
	其创新点主要集中在共识机制、智能合约、隐私安全和可扩展性上。
	比特币区块链由许多对等的节点组成，通过共识算法保证区块数据和交易数据的一致性，
	从而形成一个统一的分布式账本。
	
	wiki的概念定义 4
	A distributed database that is used to maintain a continuously 
	growing list of records, called blocks.
  
1.  **分布式数据存储方式**   
	* 区块的内容，链状的格式 
	* 安全性，放篡改，共同维护  
2.  一系列的技术集合： 分布式一致，p2p 密码学 共识机制 智能合约等
3. 现有：Bitcoin Ethereum Hyperledger 等
4. **Bitcoin** ：数字货币， 区块内容为公开账本

**区块链示意图**如下：
![bitcoin示例](https://upload-images.jianshu.io/upload_images/4310879-678ed118cb1ef995.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

**简要示例**如下：
![示例](https://pic4.zhimg.com/80/v2-dd9fb9f7baa868db6c351b85a76b49c3_hd.jpg)

**区块链架构示意图**如下：
![区块链架构](http://cdn.8btc.com/wp-content/uploads/2016/10/blockchain_overview.png)


##区块链的存储：
存储数据按照区块的形式： **区块头**和数据部分   
**以下是比特币区块的内容：**
![bitcoin区块内容](https://bitsonblocks.files.wordpress.com/2015/09/bitcoin_blockchain_infographic1.jpg?w=1188)

**bitcoin**

1.  **区块内容（账本）**   
	* 区块头：
	* 交易内容：
bitcoin交易：
![bitcoin交易](https://res.infoq.com/articles/bitcoin-and-block-chain-part04/zh/resources/01.JPG)
![tx input](https://upload-images.jianshu.io/upload_images/1367447-5124f07dc5ad6ddb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/570)
![tx output](https://upload-images.jianshu.io/upload_images/1367447-860caebcf220581f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/570)


	* 链状的形式: 安全性，防篡改，（时间戳和hash）

构建区块头和工作量证明：
![构建的区块头](https://upload-images.jianshu.io/upload_images/4310879-9ad72558588bc2b5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

2.  **地址和钱包**
	* 脚本：锁定和解锁
	* 交易实例：

地址算法：
![地址算法](https://res.infoq.com/articles/bitcoin-and-block-chain-part03/zh/resources/001.png)

![示例](https://upload-images.jianshu.io/upload_images/1367447-59384e54521a885c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

锁定脚本的逻辑格式:

比特币数量 | 来源  | 锁定地址
--- | ----  | ------
10  | 挖矿   | AAAAA
0.1  | 转账   | BBBBB

解锁脚本的逻辑格式：

解锁地址 | 解锁
------------- | -------------
AAAAA  | 地址AAAAA的公钥、地址AAAAA用私钥对前一区块头哈希散列值的签名
	
##挖矿行为：
1.  **创建新区块**   
	* 做账本：构建区块
	* 供应币：报酬
	* 保证安全：链状 共识

2.  **分布式，去中心化**
	* 工作量证明： pow（难于寻找，易于确认）
	* 共识机制： 最长链 

bitcoin工作量证明：
![Merkle树示例](https://res.infoq.com/articles/bitcoin-and-block-chain-part02/zh/resources/003.png)

3.  **构建区块**
	* 构建区块头： 工作量证明，找到符合要求proof 
	* 构建全部交易：
	* 确认区块：
	* 最长链验证：
	* 共识攻击：篡改难度非常高


##相关技术：
1.  **密码学**   
	* hash算法： < RIPEMD160 地址生成算法， SHA256 公钥 秘钥算法 > （抗碰撞）
	* merkle树：

Merkle树示例：
![Merkle树示例](https://res.infoq.com/articles/bitcoin-and-block-chain-part02/zh/resources/002.png)


2.  **共识算法**
	* 分布式共识：
	* 工作量证明：算力 
	* 其他方法： 
3.  **智能合约**
	* 以太坊
	* 合约
3.  **联盟链和私有链**
	* 超级账本  

#Bitcoin代码阅读：
本文比特币源码下载[**地址**](https://github.com/bitcoin/bitcoin)

##代码结构：


##核心入口：

bitcoin中main函数运行流程：
![bitcoin区块内容](https://upload-images.jianshu.io/upload_images/4045346-be60df7267dc3ef4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/554)




	
	  