---
title: Power BI 数据模型的版本控制
description: OData 服务公开的数据模型
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: c5efb5198b604d9ee3eb6e0bd2691e98d807261b
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762044"
---
# <a name="data-model-versioning"></a>数据模型版本控制

OData 服务公开的数据模型（例如 Power BI 数据模型）将定义 OData 服务及其客户端之间的合约。 仅允许服务将其模型扩展到不会中断现有客户端的程度。 中断更改（例如删除属性或更改现有属性的类型）要求在不同的服务根 URL 上为新模型提供一个新服务版本。  
  
以下数据模型添加项均视为安全，且无需使用服务来对其入口点进行版本控制。  
  
* 添加一个属性，其既可为 null 也可具有默认值；如果它与现有动态属性具有相同的名称，则该属性的类型（或基类型）必须与现有动态属性的类型相同  
* 添加一个导航属性，其既可为 null 也可集合取值；如果它与现有动态导航属性具有相同的名称，则该属性的类型（或基类型）必须与现有动态导航属性的类型相同  
* 将新的实体类型添加到该模型  
* 将新的复杂类型添加到该模型  
* 添加新的实体集  
* 添加新的单一实例  
* 添加操作、函数、操作导入或函数导入
* 添加一个操作参数，该参数可以为 null  
* 添加类型定义或枚举  
* 向模型元素添加任一批注，它无需由客户端识别，即可与服务正确交互  
  
客户端应准备好相关服务，以便为其模型执行此类增量式更改。 客户端尤其应准备好接收之前未由服务定义的属性和派生类型。  
  
服务不应更改其数据模型，具体取决于经过身份验证的用户。 如果数据模型依赖于用户或用户组，则在将完整模型与用户可见的具有受限授权的模型相比较时，所有更改都必须为安全更改，如本部分中所定义。  
  
有关 OData 数据模型标准的详细信息，请参阅 [OData 版本 4.0 第 1 部分：协议及勘误表 02](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)。  
  
## <a name="see-also"></a>另请参阅
[Power BI REST API 概述](https://docs.microsoft.com/rest/api/power-bi/)  