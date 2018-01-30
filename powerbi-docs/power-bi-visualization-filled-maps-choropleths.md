---
title: "Power BI 中的着色地图（等值线图）（教程）"
description: "文档 - 有关在 Power BI 中创建着色地图（等值线图）的教程"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 08b01048823d928d5c07fd4ad86764bc13921a31
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="filled-maps-choropleths-in-power-bi-tutorial"></a>Power BI 中的着色地图（等值线图）（教程）
着色地图使用明暗度、颜色或图案来显示不同地理位置或区域之间的值在比例上有何不同。  使用从浅（不太频繁/较低）到深（较频繁/较多）的明暗度快速显示这些相对差异。    

![](media/power-bi-visualization-filled-maps-choropleths/large_map.png)

## <a name="what-is-sent-to-bing"></a>发动到必应的数据
Power BI 与必应相集成，提供默认地图坐标（一个称为地理编码的过程）。 在 Power BI 服务或 Power BI Desktop 中创建地图可视化效果时，“位置”、“纬度”和“经度”存储桶中的数据（用于创建该可视化效果）将发送到必应。

有关发送到必应的数据的详细信息，以及提高地理编码成功率的提示，请参阅[地图可视化效果的提示和技巧](power-bi-map-tips-and-tricks.md)。

## <a name="when-to-use-a-filled-map"></a>何时使用着色地图
着色地图适用情况：

* 要在地图上显示定量信息。
* 要显示空间模式和关系。
* 你的数据已进行标准化处理。
* 处理社会经济数据时。
* 当定义的区域很重要时。
* 要获取跨地理位置的分布的概况。

## <a name="create-a-basic-filled-map"></a>创建基本的着色地图
在此视频中，Kim 将创建基本地图并将其转换为着色地图。

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


1. 若要创建你自己的着色地图，请[下载销售和市场营销示例](sample-datasets.md)，具体方法是登录 Power BI，然后依次选择“获取数据”**\>“示例”“销售和市场营销”\>\>“连接”。**
2. 出现成功消息时，选择“查看数据集”。 
   
   ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-view-dataset.png)
3. Power BI 将在[编辑视图](service-interact-with-a-report-in-editing-view.md)下打开一个空白的报表画布。
   
    ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-blank-canvas.png)
4. 从“字段”窗格中，选择“地区”\>“状态”字段。    
   
   ![](media/power-bi-visualization-filled-maps-choropleths/img002.png)
5. [将图表转换](power-bi-report-change-visualization-type.md)为着色地图。 请注意，州现在位于位置框中。 必应地图使用位置框中的字段创建地图。  该位置可以是各种有效位置：国家/地区、州、县、市、邮政编码或其他邮政编码等。必应地图可提供世界各地的着色地图形状。 如果“位置”框中没有有效的条目，则 Power BI 无法创建着色地图。  
   
   ![](media/power-bi-visualization-filled-maps-choropleths/img003.png)
6. 筛选地图使其只显示美国大陆。
   
   a.  在“可视化效果”窗格底部，查找筛选器区域。
   
   b.  将鼠标悬停在州上方，然后单击 v 形展开图标  
   ![](media/power-bi-visualization-filled-maps-choropleths/img004.png)
   
   c.  在全部旁边添加复选标记，并删除 AK 旁边的复选标记。
   
   ![](media/power-bi-visualization-filled-maps-choropleths/img005.png)
7. 选择“销售数据”\>“消费意愿”以将其添加到“颜色饱和度”框中。 “颜色饱和度”中的字段可很好地控制地图明暗度。  
   ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-color-saturation.png)
8. 着色地图为绿色，其中浅绿代表较低的消费意愿数值，深绿代表较高、较积极的消费意愿。  此处我突出显示了怀俄明州 (WY)，可以看见该州的消费意愿很好，为 74。  
   ![](media/power-bi-visualization-filled-maps-choropleths/img007.png)
9. [保存报表](service-report-save.md)。

## <a name="highlighting-and-cross-filtering"></a>突出显示和交叉筛选
有关使用筛选器窗格的信息，请参阅[向报表添加筛选器](power-bi-report-add-filter.md)。

突出显示着色地图中的某个位置可交叉筛选报表页上的其他可视化效果，反之亦然。 

若要执行此操作，请将着色地图复制并粘贴到“销售和营销”报表的“情绪”页。 

1. 在着色地图中选择一个州。  这样可以突出显示页面上的其他可视化效果。 例如，选择德克萨斯州，显示消费意愿为 74，德克萨斯州位于中部地区 \#23，并且大部分销量来自中型商店和便利店。   
   ![](media/power-bi-visualization-filled-maps-choropleths/img008.png)
2. 在折线图上，在否和是之间切换。 这可以筛选着色地图使其显示 VanArsdel 和 VanArsdel 的竞争产品的消费意愿。  
   ![](media/power-bi-visualization-filled-maps-choropleths/img009.gif)

## <a name="considerations-and-troubleshooting"></a>注意事项和疑难解答
地图数据可以是模棱两可的。  例如，可以有法国的巴黎，但也可以有德克萨斯州的巴黎。 地理数据可能存储在单独的列中 – 城市名称的列、州或省名称的列，等等 — 因此必应可能无法区分巴黎是哪个巴黎。 如果数据集已经包含纬度和经度数据，那么 Power BI 可以提供特殊的字段使地图数据不再模棱两可。 只需将包含纬度数据的字段拖放到“可视化效果”\>“纬度”区域。  对经度数据执行相同操作。  
![](media/power-bi-visualization-filled-maps-choropleths/pbi_latitude.png) 

如果你具有编辑 Power BI Desktop 中的数据集的权限，则观看该视频有助于解决地图数据的模糊性。

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

如果你没有访问纬度和经度数据的权限，则[按照这些说明来更新你的数据集](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7)。

有关地图可视化效果的更多帮助，请参阅 [Tips and tricks for map visualizations（地图可视化效果的提示和技巧）](power-bi-map-tips-and-tricks.md)。

## <a name="next-steps"></a>后续步骤
[将着色地图添加为仪表板磁贴（固定视觉对象）](service-dashboard-tiles.md)    
 [向报表添加可视化效果](power-bi-report-add-visualizations-i.md)  
 [Power BI 中的可视化效果类型](power-bi-visualization-types-for-reports-and-q-and-a.md)    
 [更改所使用的可视化效果类型](power-bi-report-change-visualization-type.md)      
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)
