---
title: "データ型の概要 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Boolean data type [Visual Basic], supported types in Visual Basic
- storage [Visual Basic], order of storage
- data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], supported types in Visual Basic
- notation [Visual Basic], scientific
- memory requirements, data types
- user-defined data types [Visual Basic], Visual Basic
- Date data type [Visual Basic], Visual Basic
- Visual Basic, data types
- storage [Visual Basic], allocation
- Integer data type [Visual Basic], Visual Basic data types
- storage [Visual Basic], space
- Variant data types [Visual Basic], supported types in Visual Basic
- Char data type [Visual Basic], Visual Basic data types
- intrinsic data types [Visual Basic]
- memory consumption [Visual Basic], data types
- single-precision numbers
- data types [Visual Basic], order of storage
- Long data type [Visual Basic], supported types in Visual Basic
- String data type [Visual Basic], Visual Basic data types
- storage order, data types
- StructLayoutAttribute class, Visual Basic data type storage
- scientific notation
- Double data type [Visual Basic], Visual Basic data types
- Byte data type [Visual Basic], Visual Basic data types
- Object data type [Visual Basic], supported types in Visual Basic
- data types [Visual Basic], storage allocation
- double-precision numbers
- data types [Visual Basic], summary
- dates [Visual Basic], data types
- strings [Visual Basic], data types
- memory consumption
- storage order, controlling in Visual Basic
- data types [Visual Basic], memory requirements
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f69a112718eed7bb7baaff9bdffd110865c21081
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="data-type-summary-visual-basic"></a>データ型の概要 (Visual Basic)
次の表は、Visual Basic データ型、サポートする共通言語ランタイムの型、その公称記憶域割り当て、およびその値の範囲を示します。  
  
|Visual Basic の型|共通言語ランタイム型の構造|公称記憶域の割り当て|値の範囲|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|プラットフォームの実装によって異なります|`True` または `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 バイト|0 ~ 255 (符号なし)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (単一の文字)|<xref:System.Char>|2 バイト|0 ~ 65535 (符号なし)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 バイト|0:00:00 (深夜) から 9999 年 12 月 31 日の 11時 59分: 59 PM 0001 年 1 月 1 日|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 バイト|79,228,162,514,264,337,593,543,950,335 +/-0 ~ (7.9... +/-E + 28) <sup>†</sup>なしで、小数点以下の桁数の右側の桁数が 28 数値 +/-0 ~; 10 進数のポイント<br /><br /> 0 以外の最小数は、(1 e ~ 28) +/-+/-0.0000000000000000000000000001 <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)(倍精度浮動小数点数)|<xref:System.Double>|8 バイト|-- を 4.94065645841246544E-324 <sup>†</sup>負の値です。<br /><br /> 4.94065645841246544E-324 1.79769313486231570 e + 308 ~ <sup>†</sup>正の値|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 バイト|-2,147, 483,648 ~ 2,147, 483,647 (署名)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md)(長整数)|<xref:System.Int64>|8 バイト|9,223,372,036,854,775,807 を通じて-9,223,372,036,854,775,808 (9.2... E + 18 <sup>†</sup>) (署名)|  
|[Object](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object>(クラス)|32 ビット プラットフォームでは 4 バイト<br /><br /> 64 ビット プラットフォームでは 8 バイト|型の変数に格納できる任意の型`Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 バイト|-128 ~ 127 (署名)|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md)(短整数型)|<xref:System.Int16>|2 バイト|-32,768 ~ 32,767 (署名)|  
|[Single](../../../visual-basic/language-reference/data-types/single-data-type.md)(単精度浮動小数点数)|<xref:System.Single>|4 バイト|-3.4028235 e + 38 ~ - 1.401298E-45 <sup>†</sup>負の値です。<br /><br /> 1.401298E-45 3.4028235 e + 38 ~ <sup>†</sup>正の値|  
|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)(可変長)|<xref:System.String>(クラス)|プラットフォームの実装によって異なります|約 20億 Unicode 文字に 0|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 バイト|0 ~ 4,294,967,295 (符号なし)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 バイト|0 ~ 18,446,744,073,709,551,615 (1.8... E + 19 <sup>†</sup>) (符号なし)|  
|[ユーザー定義](../../../visual-basic/language-reference/data-types/user-defined-data-type.md)(構造)|(から継承<xref:System.ValueType>)|プラットフォームの実装によって異なります|構造体の各メンバーにによって決まり、そのデータ型と他のメンバーの範囲に依存しない範囲|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 バイト|0 ~ 65,535 (符号なし)|  
  
 <sup>†</sup>で*科学的表記法*、"E"が 10 の累乗を指します。 つまり、3.56 e + 2 は 3.56 x 10 ように<sup>2</sup>または 356 を表し、3.56-2 は 3.56/10<sup>2</sup> 0.0356 またはします。  
  
> [!NOTE]
>  テキストを含む文字列を使用して、<xref:Microsoft.VisualBasic.Strings.StrConv%2A>を 1 つのテキスト形式から変換する関数。  
  
 を、宣言ステートメントでのデータ型を指定するだけでなく、型文字を使用してプログラミング要素のデータ型を強制できます。 参照してください[文字を入力して](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)です。  
  
## <a name="memory-consumption"></a>メモリの使用量  
 基本データ型を宣言する場合は、そのメモリ消費量がの公称記憶域の割り当てと同じであると仮定する安全ではありません。 次の考慮事項のため次に示します。  
  
-   **記憶域の割り当て。** 共通言語ランタイムは、アプリケーションが実行されているプラットフォームの現在の特性に基づく記憶域を割り当てることができます。 メモリがほぼいっぱいの場合は、近くで、宣言された要素をできるだけ一緒にパックこと可能性があります。 それ以外の場合に、パフォーマンスを最適化するために自然なハードウェアの境界をメモリ アドレスを満たしている可能性があります。  
  
-   **プラットフォームの幅。** 64 ビット プラットフォーム上で記憶域の割り当ては、32 ビット プラットフォームでの割り当てと異なります。  
  
### <a name="composite-data-types"></a>複合データ型  
 同じ考慮事項は、構造体や配列などの複合データ型の各メンバーに適用されます。 単に型のメンバーの公称記憶域の割り当てを一緒に追加することに依存することはできません。 さらに、これには、次のよう、その他の考慮事項があります。  
  
-   **オーバーヘッドです。** 一部の複合型では、追加のメモリ要件があります。 たとえば、配列は配列自体および各ディメンションに余分なメモリを使用します。 32 ビット プラットフォームでは、このオーバーヘッドは現在、12 バイト + ディメンションごとに 8 バイトです。 64 ビット プラットフォーム上でこの要件は 2 倍になります。  
  
-   **記憶域のレイアウトです。** メモリ内に格納される順序は、宣言の順序と同じ安全に想定することはできません。 2 バイトまたは 4 バイト境界などのバイトのアラインメントについて想定することもできません。 クラスまたは構造体を定義してそのメンバーのストレージ レイアウトを制御する必要があります、適用することができる場合、<xref:System.Runtime.InteropServices.StructLayoutAttribute>属性をクラスまたは構造体。  
  
### <a name="object-overhead"></a>オブジェクトのオーバーヘッド  
 `Object`を参照する、基本または複合データ型を使用してデータ型に含まれているデータだけでなく 4 バイト。  
  
## <a name="see-also"></a>関連項目  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [データ型変換関数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [変換の概要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [型文字](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [データ型の有効な使用方法](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
