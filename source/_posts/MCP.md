---
title: MCP
date: 2026-11-4 20:00:00
tags:
  - 学习记录
categories:
  - 学习笔记
---



##### 定义

MCP（Model Context Protocol，模型上下文协议）是一套标准化的通讯协议，旨在规范AI模型和外部工具、数据源的连接方式，由Anthropic（Claude母公司）于2024年11月提出。

MCP就像是AI时代的USB-C通用接口，开发者只需按标准开发一次MCP Server，任何支持该协议的AI应用都能即插即用。

通过MCP协议，AI应用和MCP Server可以建立多对多的双向数据流。

##### 流程
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67299076/1792999976976-54f0c8b3-b9db-4312-aa20-4d275035b9fc.png)

MCP可以理解为对Function Call的进一步封装和拓展，工具的定义和调用者由AI应用变为MCP服务器。

除了工具调用，MCP还支持管理资源（Resources）和提示词（Prompts）。前者是MCP服务器提供的被动数据源（文件、数据库），可以被AI应用主动获取，作为模型上下文传递。后者是MCP服务器提供的预置提示词模板，也是由AI应用主动获取后发给大模型，当然，AI应用可以和用户交互，补全模板中的关键信息。

最常用的是工具（Tools）模块。

