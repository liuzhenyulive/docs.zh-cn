---
title: UI 自动化线程处理问题
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, threading issues
- threading issues with UI Automation
ms.assetid: 0ab8d42c-5b8b-481b-b788-2caecc2f0191
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 7d8df325d18c3657d4955fa534d29bb7fdbc595c
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846495"
---
# <a name="ui-automation-threading-issues"></a>UI 自动化线程处理问题
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 由于 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 使用 Windows 消息的方式，当客户端应用程序尝试在 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 线程上与自己的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 进行交互时，可能发生冲突。 这些冲突可导致执行极其缓慢或者甚至会导致应用程序停止响应。  
  
 如果客户端应用程序旨在与桌面上的所有元素（包括自己的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]）进行交互，则应在单独线程上调用所有的 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 。 这包括查找元素（例如，通过使用 <xref:System.Windows.Automation.TreeWalker> 或 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 方法）和使用控件模式。  
  
 在 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 事件处理程序内调用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 是安全的，因为事件处理程序始终在非[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 线程上调用。 但是，当订阅可能来源于客户端应用程序的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]的事件时，必须在非 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>线程上调用[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 或相关方法。 删除同一线程上的事件处理程序。
