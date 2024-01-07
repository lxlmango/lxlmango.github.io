# 系统架构设计师---绪论


# 绪论

* **架构的定义**
   架构是体现在组件中的一个系统的基本组织，它们彼此的关系与环境的关系及指导它的设计和发展的原则
___

* **系统架构师角色**
   系统架构师就是项目的总设计师，他是一个即需要掌握整体又需要洞悉局部瓶颈，并根据具体的业务场景给出解决方案的总体设计人员；他需要确定和评估系统需求，给出开发规范，搭建系统实现的核心架构，并澄清技术细节，扫清主要难点的技术人员 ；他要掌握技术团队的能力需要，给出项目管理方法，采用合适的生命周期模型，具备以自身为核心形成团队的能力，并在项目进度计划和经费分配等方面开展评估，以预防项目风险。
___

* **架构设计的作用**
   1.解决相对复杂的需求分析问题
   2.解决非功能属性在系统占据主要位置的设计问题
   3.解决生命周期长，扩展性需求高的系统整体结构问题
   4.解决系统基于组件需要的集成问题
   5.解决业务流程再造难的问题
___

* **系统架构是什么**
   系统架构是系统的一种整体的高层次的结构表示，是系统的骨架和根基，支撑和链接各个部分，包括组件、连接件、约束规范以及指导这些内容设计与演化的原理，他是刻画系统整体抽象结构的一种手段，也决定了系统的健壮性和生命周期的长短
___

* **系统的定义**
   系统是组织起来完成某一特定功能或一组功能的组件集。系统这几术语还包括了单独的应用程序、传统意义上的系统、子系统、系统之系统、产品线、整个企业及感兴趣的其他集合。系统用于完成其环境中的一个或多个任务。
___

* **架构设计师的定义**
架构设计师是系统开发的主体角色，他们通过执行一系列活动来实施架构设计。架构设计通过生成过程形成最终的产品架构，架构设计师的成果师创建架构。架构设计师是负责系统架构的人、团队或者组织，是系统或产品线的设计责任人，是一个负责理解和管理并最终确认和评估非功能系统需求、给出开发规范、搭建系统实现的核心架构，对整个软件架构、关键构建和接口进行总体设计并澄清关键技术细节的高级技术人员。
___

* **架构设计师需要具备的专业素质**
* 掌握业务领域知识、
* 掌握技术知识
* 掌握设计知识
* 具备编程技能
* 具备沟通能力
* 具备决策能力
* 知道组织策略
* 是个谈判专家
___

* **软件架构的常用分类**
1. **分层架构**
分层架构是最常见的软件架构，也是事实上的标准架构，这种架构将软件分成若干个水平层，每一层都有清晰的角色和分工，不需要指导其他层的细节，层与层之间通过接口进行通信。分层架构通常明确约定软件一定要分多少层，常见的分层架构为四层
* 表现层：用户界面，负责视觉和用户互动
* 业务层：实现业务逻辑
* 持久层：提供数据，SQL语句就放在这一层
* 数据层：保存数据

2. **事件驱动架构**
事件是状态发生变化时软件发出的通知，事件驱动架构是通过事件进行通信的软件架构，有**4个**组成部分
* 事件队列：接收事件的入口
* 事件分发器：将不同的事件分到不同的业务逻辑单元
* 事件通道：分发器与处理器之间的联系渠道
* 事件处理器：实现业务逻辑，处理完成后发出事件，触发下一步操作

3. **微核架构**
微核架构又称为插件架构，是指软件的内核相对较小，主要功能和业务逻辑都通过插件实现，内核通常只包含系统运行的最小功能，插件则是相互独立的，插件之间的通信应该减少到最低，避免出现相互依赖问题

4. **微服务架构**
微服务架构师服务导向(SOA)的升级，每个服务都是一个独立的部署单元，这些单元是分布式的，互相解耦，通过远程通信协议(比如REST,SOAP)联系，三种实现模式
* RESTFULAPI模式：服务通过API提供，云服务就属于这一类
* RESTFUL应用模式：服务通过传统的网络协议或者应用协议提供，背后通常是一个多功能应用程序，常见于企业内部
* 集中消息模式：采用消息代理，可以实现消息队列、负载均衡、统一日志和异常处理，缺点是会出现单点失败，消息代理可能需要做成集群

5. **云架构**
云架构主要解决扩展性和并发性问题，是最容易扩展的架构，它的扩展性体现在将数据复制到内存中，变成可复制的内存数据单元，然后业务处理能力封装成一个个处理单元。若访问量增加，就增加处理单元，访问量减少则关闭处理单元，由于没有中央数据库，所以扩展性最大的瓶颈消失了，由于每个处理单元的数据均在内存里，需要进行数据持久化，主要分为
* 处理单元，实现业务逻辑
* 虚拟中间件：负责通信、保持会话控制、数据复制、分布式处理和处理单元部署，包含四个组件
 ①消息中间件: 管理用户请求和会话控制，当一个请求进来后，它决定分配给哪个处理单元
 ②数据中间件: 将数据复制到每一个处理单元，即数据同步，保证每个处理单元都得到同意的数据
 ③处理中间件: 可选的，如果一个请求涉及不同类型的处理单元，该中间件负责协调处理单元
 ④部署中间件: 负责处理单元的启动和关闭，监控负载和响应事件，当负载增加，则新启动处理单元，负载降低，则关闭处理单元





