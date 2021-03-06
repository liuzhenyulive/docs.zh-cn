---
title: DevOps 协作基础的容器
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 6c7de61f421cf2c45cd3c5ee9afc5a388e985b52
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105558"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>DevOps 协作基础的容器

由容器和 Docker 技术的性质，开发人员可以共享及其软件和依赖关系轻松地与 IT 运营和生产环境同时消除典型的"it works 我的计算机上"理由。 容器解决不同的环境之间的应用程序冲突。 间接，容器和 Docker 使开发人员和 IT 运营部门更靠近在一起，使其更方便地有效地进行协作。 采用容器工作流将许多客户提供他们已查找但以前必须实现通过更复杂的配置，对于版本和生成管道的 DevOps 连续性。 容器简化在 DevOps 中生成或测试/部署管道。

![](./media/image1.png)

每个容器化 Docker 应用程序生命周期中的"角色"的图 2-1： 主工作负荷

借助 Docker 容器，开发人员自己什么是在 （应用程序和服务和的框架和组件的依赖项） 的容器和容器和服务的行为方式为应用程序的服务的集合是由在一起。 Docker-compose.yml 文件，或那些可称为中定义多个容器的依存关系*部署清单*。 同时，IT 运营团队 （IT 专业人员和管理） 可以专注于生产环境; 的管理基础结构;可伸缩性;监视;并且，从根本上讲，确保，应用程序是否可以实现正确的最终用户，而无需知道各种容器的内容。 因此，名称"容器，"重新调用到实际传送容器的相似之处。 因此，容器的内容的所有者需要不考虑自身与如何容器将被传送、 传输和传送的公司传输从起点到其目标的容器而无需知道或有关内容管理。 类似的方式，开发人员可以创建和拥有而无需自己考虑"传输"机制 Docker 容器中的内容。

在图 2-1 的左侧支柱，开发人员编写和 Docker 容器中本地运行代码，通过使用用于 Windows 的 Docker 或 mac。 它们通过使用指定的基的操作系统以及到 Docker 映像生成其代码的生成步骤运行 Dockerfile 定义的代码的运行环境。 开发人员定义的一个或多个映像将交互使用前面提到*docker-compose.yml*文件部署清单。 在完成其本地开发时, 它们推送其应用程序代码加上的 Docker 配置文件到他们选择 （即，Git 存储库） 的代码存储库。

DevOps pillar 定义使用的代码存储库中提供的 Dockerfile 生成 – 连续集成 (CI) 管道。 CI 系统从所选的 Docker 注册表中提取基本容器映像，并生成应用程序的自定义 Docker 映像。 映像然后验证和推送到用于部署到多个环境 Docker 注册表。

在右侧支柱，团队管理的操作部署应用程序和在监视的环境和应用程序，以便它们可以提供反馈和有关如何应用程序可能由开发团队的见解时的生产环境中的基础结构改进。 容器应用程序通常在使用容器 orchestrators 的生产环境中运行。

两个团队协作通过提供作为一个协定，从而大大提高应用程序生命周期中的两个团队的协作时分离问题的基础平台 （Docker 容器）。 开发人员拥有容器内容、 其运行环境和容器相互依赖关系，而运营团队采用清单以及生成的映像，并在其业务流程系统中运行它们。

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>泛型端到端 Docker 应用程序生命周期工作流简介

图 2-2 提供更详细的工作流 Docker 应用程序生命周期，将此实例中重点放在特定的 DevOps 活动和资产。

![](./media/image2.png)

Docker 容器化应用程序生命周期图 2-2： 高级工作流

所有内容开头的开发，人员开始在内部循环工作流中编写代码。 内部循环阶段是开发人员在其中定义发生之前将代码推送到代码存储库 （例如，例如 Git 源代码管理系统） 的所有内容。 提交后，存储库中将触发持续集成 (CI) 和工作流的其余部分。

内部循环基本上包含"与代码一样，""，""test"和"调试，"以及其他步骤直接之前运行本地运行应用程序的典型步骤。 这是当开发人员运行并测试 Docker 容器形式的应用。 内部循环工作流将在以下各节中所述。

返回采用一个步骤，若要查看端到端工作流，DevOps 工作流不只是一种技术或工具集： 它是需要区域性演变观念。 它是人员、 流程和相应的工具，以使您的应用程序生命周期更快且更可预测。 通常采用容器化工作流的企业重构其组织来表示人员和匹配的容器化工作流的过程。

DevOps 在其中完成练习可帮助团队更快地响应一起竞争压力通过自动化，这会导致提高可跟踪性和可重复的工作流以代替易出错的手动过程。 组织还可以更有效地管理环境并实现与本地和云资源的组合的成本节约以及紧密集成的工具。

在实现 Docker 应用程序工作 DevOps 流时，你将看到 Docker 的技术都位于你的开发框至生成测试 CI 阶段中，内部循环 （代码，请运行、 调试） 中工作的同时从工作流中，几乎每个阶段，当然，在生产环境和过渡环境和时向这些环境中部署你的容器。

改善质量做法有助于识别在开发周期早期，从而减少修复它们的成本的缺陷。 通过在映像中包括的环境和依赖关系和采用的跨多个环境中部署的相同映像的理念，你将提升提取使部署更可靠的特定于环境的配置的专业。

获取通过有效检测 （监视和诊断） 的丰富数据深入性能问题和用户行为，以指导将来的优先级和投资。

DevOps 应视为一种部署模式，而非目的。 它应以增量方式实现通过相应地指定了作用域项目从中演示成功、 学习和发展。

## <a name="benefits-of-devops-for-containerized-applications"></a>DevOps 的容器化应用程序的优点

下面是一些提供稳定的 DevOps 工作流的最重要的好处：

-   提供更高质量软件更快且更好的符合性

-   更早版本和更划算一些驱动器的持续改进和调整

-   提高透明度和利益干系人参与建立和运行软件之间的协作

-   控制成本，并更有效地利用设置的资源，同时可尽量减少安全风险

-   即插很好地与你现有的 DevOps 投资，包括在开放源代码中的投资的很多

>[!div class="step-by-step"]
[上一页](index.md)
[下一页](../Microsoft-platform-tools-containerized-apps/index.md)
