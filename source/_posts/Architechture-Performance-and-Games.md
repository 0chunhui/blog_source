title: 'Architechture, Performance, and Games'
date: 2015-05-27 09:21:51
tags: GameProgrammingPatterns
---

## Software Architecture ##

***Good design means that when I make a change, it's as if entire program was crafted in anticipantion of it.***

松耦合的优点是显而易见的，可扩展性，可维护性... 
***Decouple everything and you'll be able to code like the wind.***
这种感觉就是为什么人们对抽象、模块化、设计模式以及软件架构感到兴奋。
一个架构良好的程序，在其中工作是一种非常愉悦的体验，每个人都会享受优秀的架构带来的高效。

## At What Cost ##

***But, like everything in life, it doesn't come free. ***
好的架构需要付出很大的努力，并严格遵守其中的规则。
每次你添加一个新的特性就需要努力的使它优雅的与现有的系统集成。
你需要思考哪些点需要解耦，并且在这些点引入抽象。
同样，你还要决定可以创建哪些可扩展性，将来可以在此基础简单修改。

***It is where it starts to get tricky. ***
每当你增加一层抽象，或者在某个地方支持了可扩展，你预测以后会用到灵活性。
这样会在你游戏里增加代码和复杂度，需要花一定的时间开发，调试，和维护。
如果你预测对了，那么你的付出就得到了回报。
***But predicting the future is hard. ***
如果那个模块根本就没有作用，它迅速编的actively harmful. 毕竟你要处理更多代码。

## Performance and Speed ##

***Many patterns that make your code more flexible rely on virtual dispatch, interfaces, pointers, messages, and other 
mechanisms that all have at least some runtime cost.***

所以，关于效率和抽象没有固定的答案。让你的程序更灵活，你就可以迅速建立游戏原型，但是会有一些性能损失。同样，优化你的
代码会让它不是那么灵活。



***Abstraction and decoupling make evolving your program faster and easier, 
but don’t waste time doing them unless you’re confident the code in question needs that flexibility.***



