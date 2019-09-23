<p style="display:inline">

<img src="https://img.shields.io/badge/build-failing-red.svg?style=for-the-badge&logo=appveyor"/>
<img src="https://img.shields.io/badge/schedule-5%25-orange.svg?style=for-the-badge&logo=appveyor"/>
</p>

<p align="center">
<img width="150" src="images/logo.png" alt="Degage Logo">
</p>


<h1 align="center">DEGAGE 开发平台</h1>
<p style="display:inline">
<a href="README_en-US.md" title="english description"><img src="https://img.shields.io/badge/language-EN--US-orange.svg?style=for-the-badge"/></a>
</p>
<h2><p align="center">前言</p></h2>
 DEGAGE 是一个为软件开发整个生命周期中提供各种各样工具与一系列分布式组件与技术方案的平台，我们希望无论在开发生命周期中从事何种工作的人，都可以享受到平台带来的便利，并为公司或个人带来统一快速的开发框架以及经验积累的容器。  

 为不同的人员我们提供不同的辅助。
 * 为开发人员：我们提供丰富的基础类库、覆盖各个平台UI组件、多样化的服务组件、与 Visual Studio 紧密集成的协作工具、快速寻错调式工具、用于快速成型的开发框架。  
 * 为实施/维护人员：我们提供自动化部署工具，从云到客户的主机，你可以快速的迭代产品，监控各个终端，通过平台在线收集客户的需求，另外我们可以收集您多年的维护经验，并以此为您构建得心应手的工具，您可以在线/离线使用它们。
 * 为项目经理：平台拥有灵活 **功能组件** 模型，所有按照规范开发的功能组件都可以重复利用并协同工作，您可以最大程度上利用其他产品已有功能组件，结合平台提供的基础框架，快速构建出符合客户要求的全新产品。
 * 为..
 * 为所有人：
   * 提供完善的知识库系统，分享与记录您的经验。
   * 模板系统，您可以从此处获取或构建各类图标、在线编写不同的产品文档、各类规范文档，我们尽可以减少您在创造之外的工作，并为您提供高质量的基础模板，当然，各类产品的界面模板也是必不可少的。总之，您可以在此处获取别人的灵感，分享自己的并使之成为模板中的一份。
   * ...
***

 ### 平台组件大纲

***图示***
<p align="center">
<img  src="images/outline.png" alt="Degage Logo">
</p>

***目录***

- [基础组件](#基础组件)
     - [基础类库](#基础类库)
     - [数据模型](#数据模型) （10%）[📃](data-model/DATAMODEL.md "查看对于此章的详细描述")
         - [数据描述](#数据描述)
         - [数据访问](#数据访问)
           - [数据库](#数据库)
           - [内存](#内存)
           - [文件](#文件)
         - [数据日志](#数据日志)
           - [数据变动记录](#数据变动)
           - [数据回退](#数据回退)
     - [服务模型](#服务模型)
         - [服务描述](#服务描述)
         - [服务发现](#服务发现)
         - [远程调用](#远程调用)
         - [服务一致性模型](#服务一致性模型)
- [功能组件模型](#功能组件平台)
     - [功能组件模型](#功能组件模型)
         - [组件规范](#组件规范)
         - [协同运作](#协同运作)
      - [功能组件管理系统](#功能组件管理系统)
- [文件管理系统](#文件管理系统)
- [消息组件](#消息组件)
     - [消息队列](#消息队列)
     - [消息推送模型](#消息推送模型)
- [缓存组件](#缓存组件)
     - [数据一致性模型](#数据一致性模型)
- [服务管理平台](#服务管理平台)
     - [注册中心](#注册中心)
     - [调度管理](#调度管理)
     - [互联互通](#互联互通)
- [定时作业系统](#定时作业系统)
- [知识库系统](#知识库系统)
- [模板系统](#模板系统)
- [环境管理系统](#环境管理系统)
     - [系统部署](#系统部署)
        - [自动化管理](#自动化管理)
        - [Docker部署方案](#Docker部署方案)
     - [版本控制](#版本控制)
     - [终端信息收集](#终端信息收集)
- [硬件集成平台](#硬件集成平台)
     - [交互模型](#交互模型)
     - [硬件SDK库](#硬件SDK库)
     - [交互模拟器](#交互模拟器)
- [用户界面](#用户界面)
     - [界面设计指南](#界面设计指南)
     - [界面模型](#界面模型)
     - [界面库](#界面库)
- [智能化技术平台](#智能化技术平台)
     - [图像处理与分析](#图像处理与分析)
        - [文字识别模型](#文字识别模型)
        - [图像识别模型](#图像识别模型)
     - [自然语言处理](#自然语言处理)
        - [信息结构化](#信息结构化)
     - [智能模型训练系统](#智能模型训练系统)
- [数据集成平台](#数据集成平台)
     - [数据采集中心](#数据采集中心)
     - [数据分析](#数据分析)
     - [数据可视化系统](#数据可视化系统)
     - [数据生产系统](#数据生产系统)
         - [数据模拟](#数据模拟)
         - [数据重组](#数据重组)
- [私有云平台构建方案](#私有云平台构建方案)
     - [Open Stack构建](#OpenStack)
- [高可用性技术方案](#高可用性技术方案)
     - [数据库集群构建](#数据库集群)
        - [MariaDb](#MariaDb)
        - [PostgreSQL](#PostgreSQL)
        - [Redis](#Redis)
 
### 平台组件在实际中的应用交互示例
（请您参照大纲图示中信息阅读）

#### 1. 单业务系统

<p align="center">
<img  src="images/example-application1.png" >
</p>

#### 2. 多业务系统协同

<p align="center">
<img  src="images/example-application2.png" >
</p>

#### 3.数据服务

<p align="center">
<img  src="images/example-application3.png" >
</p>


**** 
若有兴趣加入我们一起完善此平台，您可以通过TIM扫描下面的二维码，并备注您的开源项目地址。
<p>
<img width='150'  src="images/contact-tim.jpg" >
</p>