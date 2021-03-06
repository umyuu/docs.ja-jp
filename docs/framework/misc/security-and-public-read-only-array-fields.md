---
title: "セキュリティとパブリックの読み取り専用配列フィールド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86d054d3a5a4e10b8efcc3292f3a18ea37f9b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="security-and-public-read-only-array-fields"></a>セキュリティとパブリックの読み取り専用配列フィールド
読み取り専用のパブリック配列フィールドを変更できるため、境界の動作や、アプリケーションのセキュリティを定義するのには、マネージ ライブラリからの読み取り専用のパブリック配列フィールドを使用しないでください。  
  
## <a name="remarks"></a>コメント  
 .NET framework の一部のクラスには、プラットフォーム固有の境界パラメーターが含まれている読み取り専用のパブリック フィールドが含まれます。  たとえば、<xref:System.IO.Path.InvalidPathChars>フィールドは、ファイルのパス文字列の許可されていない文字を表す配列。  多くの同様のフィールドは、.NET Framework 全体にわたって存在します。  
  
 パブリックの読み取り専用フィールドの値と同様に<xref:System.IO.Path.InvalidPathChars>コードや、コードのアプリケーション ドメインを共有しているコードで変更できます。  アプリケーションの境界の動作を定義するのに次のようにパブリックの読み取り専用の配列フィールドを使用する必要がありますできません。  作成する場合は、悪意のあるコードは境界の定義を変更し、予期しない方法でコードを利用できます。  
  
 2.0 と .NET Framework の以降のバージョンでは、パブリックの配列フィールドを使用する代わりに新しい配列を返すメソッドを使用してください。  使用せずになど、<xref:System.IO.Path.InvalidPathChars>フィールドを使用してください、<xref:System.IO.Path.GetInvalidPathChars%2A>メソッドです。  
  
 .NET Framework の型が内部的には境界の種類を定義するパブリック フィールドを使用しないことに注意してください。  代わりに、.NET Framework では、別のプライベート フィールドを使用します。  これらのパブリック フィールドの値を変更しても、.NET Framework の型の動作は変わりません。  
  
## <a name="see-also"></a>参照  
 [安全なコーディングのガイドライン](../../../docs/standard/security/secure-coding-guidelines.md)
