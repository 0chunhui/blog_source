title: Command
date: 2015-05-27 09:19:00
tags:  GameProgrammingPatterns
---
  command模式是一种非常强大的模式。 GOF是这样定义它的：
	
> Encapsulate a request as an object, therebye letting users parameterize clients with different requests, queue or log requests, and support undoable operations.

  command的核心思想是把函数调用封装到对象里。
  
	
> Commands are an object-oriented replacement for callbacks.

  好吧，下面举几个栗子

  **输入配置**
 
 所有的游戏都会有这样一坨代码，读取玩家的原始输入（这些输入可能来自手柄、键盘、鼠标等），然后把这些输入的命令转化为对游戏有意义的动作。最简单的实现是这样的：
 
     void InputHandler::handleInput()
     {
			if(isPress(BUTTON_X)) jump();
			else if(isPress(BUTTON_Y)) run();
			else if(isPress(BUTTON_A)) switchWeapon();
			else if(isPress(BUTTON_B)) fire();
     ｝

 如果想硬编码玩家如入和游戏动作，这样做是没问题的。 但是大部分游戏都是允许玩家自己设置每个键对应的动作，要支持这种配置就需要在上面各种动作之间实现交换，所以我们就需要一个对象来代表一个游戏动作。

 首先定义个基类，代表可触发的游戏命令:
	
	class Command
	{
	public:
		virtual ~Command(){}
		virtual void execute() = 0;
	};
然后定义一些子类来表示具体命令：
	
	class JumpCommand: public Command
	{
	public:
		virtual void execute(){ jump(); }
	};

	class RunCommand: public Command
	{
	public:
		virtual void execute() { run(); }
	};
	
	class SwitchWeaponCommand: public Command
	{
	public:
		virtual void execute(){ switchWeapon(); }
	};

	class FireCommand: public Command
	{
	public:
		virtual void execute() { fire(); }
	};


 
 