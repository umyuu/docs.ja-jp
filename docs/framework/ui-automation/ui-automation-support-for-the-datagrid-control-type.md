---
title: "UI オートメーションによる DataGrid コントロール型のサポート"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Grid control type
- control types, Data Grid
- UI Automation, Data Grid control type
ms.assetid: a3db4a3f-feb5-4e5f-9b42-aae7fa816e8a
caps.latest.revision: "32"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 3eb60004f4ffad0b62b10cf1e3ff5f28a3bf3fef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-support-for-the-datagrid-control-type"></a>UI オートメーションによる DataGrid コントロール型のサポート
> [!NOTE]
>  このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージ <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](http://go.microsoft.com/fwlink/?LinkID=156746)」を参照してください。  
  
 このトピックでは、DataGrid コントロール型の [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] サポートに関する情報を提供します。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]でのコントロール型とは、コントロールが `ControlType` プロパティを使用するために満たす必要がある一連の条件のことです。 これらの条件には、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] のプロパティ値、およびコントロール パターンに関する特定のガイドラインが含まれます。  
  
 DataGrid コントロール型により、列で表されるメタデータを含む項目をユーザーが簡単に扱うことができます。 データ グリッド コントロールでは、項目の行と、それらの項目に関する情報の列があります。 Microsoft Vista Explorer のリスト ビュー コントロールは、DataGrid コントロール型をサポートする例です。  
  
 以下の各セクションで、DataGrid コントロール型に必要な [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、プロパティ、コントロール パターン、およびイベントを定義します。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] の要件は、 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]、 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]、 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]のいずれの場合も、すべてのデータ グリッド コントロールに適用されます。  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>必須の UI オートメーション ツリー構造  
 次の表では、データ グリッド コントロールに関連する [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューとコンテンツ ビューを示し、それぞれのビューに含まれる可能性のある内容について説明します。 詳細については、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ツリーを参照してください[UI オートメーション ツリーの概要](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)です。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー - コントロール ビュー|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー - コンテンツ ビュー|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataGrid<br /><br /> <ul><li>Header (0、1、または 2)<br /><br /> <ul><li>HeaderItem (列または行の数)</li></ul></li><li>DataItem (0 以上。階層で構造化できます)</li></ul>|DataGrid<br /><br /> -DataItem (0 以上階層で構造化できます)。|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>必須の UI オートメーション プロパティ  
 次の表に、データ グリッド コントロールに特に関連する値または定義を持つプロパティを示します。 詳細については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]プロパティを参照してください[クライアントの UI オートメーション プロパティ](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)です。  
  
|プロパティ|値|ノート|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|ノートを参照してください。|このプロパティの値は、アプリケーションのすべてのコントロールで一意である必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|ノートを参照してください。|コントロール全体を格納する最も外側の四角形。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|「ノート」をご覧ください。|四角形領域が存在する場合にサポートされます。 四角形領域の内側にクリック不可能な点が存在し、特別なヒット テストを実行する場合は、クリック可能な点をオーバーライドして提供します。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataGrid|この値は、すべての UI フレームワークで同じです。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|このプロパティの値は、常に True にする必要があります。 つまり、データ グリッド コントロールが常に [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコンテンツ ビューに存在している必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|このプロパティの値は、常に True にする必要があります。 つまり、データ グリッド コントロールが常に [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコンテンツ ビューに存在している必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|ノートを参照してください。|コントロールがキーボード フォーカスを受け取ることができる場合は、このプロパティをサポートする必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|ノートを参照してください。|静的なテキスト ラベルがある場合、このプロパティは対象のコントロールへの参照を公開する必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"データ グリッド"|DataGrid コントロール型に対応するローカライズされた文字列。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|ノートを参照してください。|データ グリッド コントロールは、通常、静的テキスト ラベルから `Name` プロパティの列を取得します。 静的なテキスト ラベルがない場合は、アプリケーション開発者が `Name` のプロパティ値を割り当てる必要があります。 `Name` プロパティの値が、編集コントロールのテキストの内容になることは決してありません。|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>必須の UI オートメーション コントロール パターン  
 次の表に、すべてのデータ グリッド コントロールでサポートされなければならないコントロール パターンを示します。 コントロール パターンについて詳しくは、「 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)」をご覧ください。  
  
|コントロール パターン|Support|ノート|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|はい|データ グリッド コントロール自体は、メタデータを格納する項目がグリッドに配置されるため、常に、グリッド コントロール パターンをサポートします。|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|状況に依存|データ グリッドをスクロールする機能はコンテンツ、およびスクロール バーが存在するかどうかによって異なります。|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|状況に依存|データ グリッドを選択する機能は、コンテンツに依存します。|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|はい|データ グリッド コントロールはサブツリー内に常にヘッダーがあるため、Table コントロール パターンがサポートされる必要があります。|  
  
 データ グリッド コンテナー内のデータ項目は、少なくとも次をサポートします。  
  
-   選択項目コントロール パターン (データ グリッドが選択可能な場合)  
  
-   スクロール項目コントロール パターン (データ グリッドがスクロール可能な場合)  
  
-   グリッド項目コントロール パターン  
  
-   テーブル項目コントロール パターン  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>必須の UI オートメーション イベント  
 次の表に、すべてのデータ グリッド コントロールでサポートされなければならない [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベントを示します。 イベントについて詳しくは、「 [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)」をご覧ください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベント|Support|ノート|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|必要|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|状況に依存|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|必要|なし|  
|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> プロパティ変更イベント。|状況に依存|コントロールで Scroll パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> プロパティ変更イベント。|状況に依存|コントロールで Scroll パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> プロパティ変更イベント。|状況に依存|コントロールで Scroll パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> プロパティ変更イベント。|状況に依存|コントロールで Scroll パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> プロパティ変更イベント。|状況に依存|コントロールで Scroll パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> プロパティ変更イベント。|状況に依存|コントロールで Scroll パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|必要|なし|  
  
<a name="List_View_Control_Example"></a>   
## <a name="date-grid-control-type-example"></a>データ グリッド コントロール型の例  
 次の図に、DataGrid コントロール型を実装するリスト ビュー コントロールを示します。  
  
 ![2 つのデータ項目を含むリスト ビュー コントロールのグラフィック](../../../docs/framework/ui-automation/media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 以下には、リスト ビュー コントロールに関連する [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューとコンテンツ ビューが表示されています。 オートメーションの各要素のコントロール パターンが、かっこ内に示されています。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー - コントロール ビュー|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー - コンテンツ ビュー|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|<ul><li>DataGrid (Table、Grid、Selection)</li><li>ヘッダー<br /><br /> <ul><li>HeaderItem "Name" (Invoke)</li><li>HeaderItem "Date Modified" (Invoke)</li><li>HeaderItem "Size" (Invoke)</li></ul></li><li>グループ"Contoso"(TableItem、GridItem、SelectionItem、テーブル *、グリッド\*)<br /><br /> <ul><li>DataItem"Accounts Receivable.doc"(SelectionItem、Invoke、TableItem\*、GridItem\*)</li><li>DataItem"Accounts Payable.doc"(SelectionItem、Invoke、TableItem\*、GridItem\*)</li></ul></li></ul>|<ul><li>DataGrid (Table、Grid、Selection)</li><li>グループ"Contoso"(TableItem、GridItem、SelectionItem、テーブル *、グリッド\*)<br /><br /> <ul><li>DataItem"Accounts Receivable.doc"(SelectionItem、Invoke、TableItem\*、GridItem\*)</li><li>DataItem"Accounts Payable.doc"(SelectionItem、Invoke、TableItem\*、GridItem\*)</li></ul></li></ul>|  
  
 * 上記の例では、コントロールの複数のレベルを含む DataGrid を示します。 グループ ("Contoso") のコントロールには、2 つのDataItem コントロール ("Accounts Receivable.doc" および "Accounts Payable.doc") が含まれています。 DataGrid と GridItem ペアは、他のレベルのペアから独立しています。 グループの下にある DataItem コントロールは、ListItem コントロール型として公開することもでき、単純なデータ要素としてではなく、選択可能オブジェクトとして、より明確に提示することができます。 この例では、グループ化されたデータ項目のサブ要素は含まれません。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Automation.ControlType.DataGrid>  
 [UI オートメーション コントロール型の概要](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [UI オートメーションの概要](../../../docs/framework/ui-automation/ui-automation-overview.md)
