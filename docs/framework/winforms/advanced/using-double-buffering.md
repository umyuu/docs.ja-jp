---
title: "ダブル バッファリングの使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d83846dcded620b74f7d276fd241a302cce1b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="using-double-buffering"></a>ダブル バッファリングの使用
ダブル バッファリングされたグラフィックスを使用して、複雑な描画操作を必要とするアプリケーションでちらつきを軽減することができます。 .NET Framework には、ダブル バッファリングの組み込みサポートが含まれています。 または、管理し、手動でグラフィックスをレンダリングできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ダブル バッファリングされたグラフィックス](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 ダブル バッファリングの概念とアウトライン .NET Framework のサポートが導入されています。  
  
 [方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 ダブル バッファリングを .NET Framework のサポート、既定値を使用する方法を示します。  
  
 [方法: バッファリングされたグラフィックスを手動で管理する](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 アプリケーションのダブル バッファリングを管理する方法を示します。  
  
 [方法: バッファリングされたグラフィックスを手動で描画する](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 ダブル バッファリングされたグラフィックスをレンダリングする方法を示します。  
  
## <a name="reference"></a>参照  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 ダブル バッファリングできるようにするメソッドを制御します。  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 グラフィックス バッファーを作成するためのメソッドを提供します。  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 アプリケーション ドメインのバッファリングされたグラフィックス コンテキストへのアクセスを提供します。
