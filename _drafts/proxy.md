---
layout: post
title: java设计模式-代理模式
categories: design
description: 代理模式
keywords: design，proxy
---

## 代理模式

使用代理模式创建代理对象，让代理对象控制目标对象的访问（目标对象可以是远程对象、创建开销大的对象或需要安全控制的对象），并且可以在不改变目标对象的情况下添加一些额外的功能。

UML

<img src="/images/posts/design/static_proxy.jpg"  />


**Subject**:抽象主题角色，抽象主题类可以是抽象类，也可以是接口，是一个最普通的的业务类型定义，无特殊要求

**RealSubject**：具体主题角色，也叫被委托角色、被代理角色。是业务逻辑的具体执行者

Proxy：代理主题角色，也叫委托类、代理类。它把所有抽象主题类定义的方法给具体主题角色实现，
并且在具体的主题角色处理完毕前后作预处理和善后工作

> 为什么Proxy和RealSubject集成/实现同一个接口？ 为了在任何使用RealSubject的地方替换成Proxy


