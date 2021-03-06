---
title: 《DevOps实践指南》
date: 2019-7-15 15:15:24
tags: 软件工程
categories: 读书
---


### 实现快速可靠的自动化测试 - 《DevOps 实践指南》

让开发人员在日常工作中创建自动化测试套件

自动化单元测试

自动化验收测试

测试团队提供自动化测试套件



- 全面且可靠的自动化测试套件，用于验证可部署状态

- 一种在验证测试失败时，可以"停掉整条生产线"的文化
- 开发人员在主干上工作，并小批量提交变更，而不是在生命周期很长的特性分支上工作



自动化测试分类：

- 单元测试：确保代码按照开发人员的设计运行
- 验收测试：通过整体测试应用，确保各个魔能模块按照设计正常工作，而且没有引入回归错误
- 集成测试：保证应用能与生产环境中其他应用和服务正确地交互



自动化测试套件的一个设计目标：能尽早地在测试中发现错误，并且减少对手工测试的依赖

要确保自动化测试可靠，最有效的一个方法是通过测试驱动开发(Test-Driven Development TDD)和验收测试驱动开发(Acceptance Test-Driven Development ATDD)



通过执行自动化测试，所有测试人员(包括测试人员)得以去做那些不能被自动化的高价值活动，如探索性测试或优化测试流程本身



执行少量可靠的自动化测试，往往优于执行大量手动测试或不可靠的自动化测试，应该专注于将能验证业务目标的测试自动化，如果放弃某个测试之后，生产环境出现缺陷，那么应该讲这个测试重新加入手动测试套件，但最终还是应该将它自动化

应该从少量可靠的自动化测试开始，并随着时间的推移不断增加，这样一来，系统的保障级别随之提高，并能快速检测出所有让代码偏离可部署状态的变更
