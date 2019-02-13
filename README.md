# 设计模式 #

* 在SDK从0到1研发期间，为了架构清晰、模块独立并使得整个系统易于扩展升级，过程中接触并使用了许多设计模式。
* 这一系列文章主要用于总结设计模式要点，其中也加入了横向思考，反思设计模式如何体现在Apple的源码设计之中，并举例如何在实际开发中自然的使用设计模式。

## 【1】基础知识 ##
* 因为设计模式大量牵扯到类图与类之间的关系，开始总结之前，先定义其表现形式。这里借助于对象建模技术(OMT, Object Modeling Technique)进行阐述。

* 类图 
  1.	协议. 协议用于在iOS中定义抽象行为，在面向接口编程中广泛使用，是设计模式中极为重要的一种表现形式。具体的类通过遵循协议实现抽象定义的行为。 在类图中以<@protocolName>表示，定义抽象行为。
  2. 抽象基类. 抽象基类也可以定义抽象行为，由派生的子类实现抽象行为。但iOS不支持多继承，使得抽象基类不够灵活，更多的时候需要配合协议一起使用。抽象基类可以定义抽象行为由子类去实现，也可以定义具体行为供子类使用。
  3. 具体子类. 具体子类遵循于抽象设计，完成具体的行为。
  4. 范畴. 范畴作为iOS中对类的扩展，与当前类保持平级状态。在类图中以(CategoryName)表示，定义扩展的具体行为。
  ![classDiagram](https://github.com/sean4app/Design-Pattern/blob/master/Resources/Images/1.ClassDiagram.png)
  
* 关系图
	1. 实例化. 表示由一个类创建了另一个类，使用虚线实心箭头，指向被创建的类。
	2. 继承协议. 表示基类或具体类遵循协议，使用虚线空心箭头，指向协议。
	3. 继承基类. 表示具体子类派生自基类，使用实线空心箭头，指向基类。
	4. 相识. 表示一个类持有另一个类的引用，使用实线实心箭头，指向持有的类。
	![relationDiagram](https://github.com/sean4app/Design-Pattern/blob/master/Resources/Images/1.RelationDiagram.png)
	

