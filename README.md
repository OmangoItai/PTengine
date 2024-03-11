# PT engine

生产传送引擎，用于模拟物质交换行为。  
在这里，只有  

- 1·生产行为  
- 2·传送行为  
- 3·消费行为  

会被全过程监控，用以日复一日地运转与观测。  
而你可以利用任何政治学、经济学的理论指导，来指挥这个纯粹的物质世界运转。创造一个特殊的商品：货币；或是用统一的计划来高效运转……经过设定的周期（通常是年）后，通过一系列的数据，来考验你的政治经济技巧。

## Prerequisite 前提
- 1·封闭生产系统
- 2·任务分为：生产、物流、消费
- 3·单元分为：生产单元、消费单元（物流单元算进生产单元）
- 4·生产行为的产品源头是自然资源；经历生产单元；终点是消费单元
- 5·任务都需要花费时间与原料投入
- 6·不分昼夜（仔细想想，的确没有必要），但需要设立周期
- 7·自然资源每周期再生量固定
## Usage 使用

你需要配置以下内容，才能使该引擎运行：
- 1·priceVictor 价格向量
- 2·naturalResources 自然资源：每年自然资源再生量
- 3·personList 自然人列表
- 4·unitList 单元列表
- 5·map 地图
- 6·priceVector 价格向量
- 7·timePeriod 时钟周期

## Unit 单元
需要为每个单元配置以下函数，以保证它们在生产和消费中实时运行：  
- Triggers: Dict[str, np.ufunc] -> Task

每个单元可以设立若干触发器。  
你可以为他添加一个**生产触发器**、或**消费触发器**，在特殊用途上，甚至可以天价**周期性触发器**。

>**Tips:** 如果你想模拟市场经济，那么应该建立一个名为 Market 的单位，并在周期性触发器中写入**收到来自任何工厂的商品，并返还它们对应的货币（一种商品）；一定周期内将库存交还源工厂，并收回对应货币**的逻辑（当然，这很粗糙）。