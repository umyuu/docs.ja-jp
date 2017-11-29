---
title: "外部関数 (F#)"
description: "ネイティブ コードで関数の呼び出しの f# 言語サポートについて説明します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="50237-104">外部関数</span><span class="sxs-lookup"><span data-stu-id="50237-104">External Functions</span></span>

<span data-ttu-id="50237-105">このトピックでは、ネイティブ コードで関数の呼び出しの f# 言語サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="50237-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="50237-106">構文</span><span class="sxs-lookup"><span data-stu-id="50237-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="50237-107">コメント</span><span class="sxs-lookup"><span data-stu-id="50237-107">Remarks</span></span>

<span data-ttu-id="50237-108">前の構文で*引数*に渡される引数を表す、`System.Runtime.InteropServices.DllImportAttribute`属性。</span><span class="sxs-lookup"><span data-stu-id="50237-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="50237-109">最初の引数は、.dll 拡張子を除いた、この関数を含んでいる DLL の名前を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="50237-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="50237-110">いずれかのパブリック プロパティの追加の引数を指定することができます、`System.Runtime.InteropServices.DllImportAttribute`クラス、呼び出し規則などです。</span><span class="sxs-lookup"><span data-stu-id="50237-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="50237-111">ネイティブ C++ の DLL を次のエクスポート関数を含む必要があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="50237-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="50237-112">次のコードを使用して、F# からこの関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="50237-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="50237-113">ネイティブ コードとの相互運用性と呼びます*プラットフォーム呼び出し*あり、CLR の機能です。</span><span class="sxs-lookup"><span data-stu-id="50237-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="50237-114">詳細については、「[アンマネージ コードとの相互運用](https://msdn.microsoft.com/library/sd10k43k.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50237-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="50237-115">そのセクションの情報は、f# に適用されます。</span><span class="sxs-lookup"><span data-stu-id="50237-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="50237-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="50237-116">See Also</span></span>

[<span data-ttu-id="50237-117">関数</span><span class="sxs-lookup"><span data-stu-id="50237-117">Functions</span></span>](index.md)