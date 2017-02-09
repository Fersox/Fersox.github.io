---
layout: post
title: 理解 Spring mvc RequestContextHolder
categories: API
description: 理解 Spring mvc RequestContextHolder
keywords: spring mvc request
---

## RequestContextHolder

### 简介

RequestContextHolder is a spring API for setting the values to any of three scopes request, session or global session. Note that in some situations, we may not be able to **get the actual request from the request**, we can simply use RequestContextHolder to get the request attributes and set the values. We have to explicitly pass the scope id as the parameter. 
	
RequestContextHolder methods：

1. **currentRequestAttributes()**：Return the RequestAttributes currently bound to the thread.
2. **getRequestAttributes()** ： Return the RequestAttributes currently bound to the thread.
3. **resetRequestAttributes()** ：Reset the RequestAttributes for the current thread.
4. **setRequestAttributes(RequestAttributes attributes)** ：Bind the given RequestAttributes to the current thread, not exposing it as inheritable for child threads.
5. **setRequestAttributes(RequestAttributes attributes, boolean inheritable)**：Bind the given RequestAttributes to the current thread.


### 应用



### 原理解析