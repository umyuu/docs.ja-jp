---
title: "型拡張 (F#)"
description: "F# 型の拡張機能が新しいメンバーの種類を追加する、定義済みのオブジェクトを許可する方法について説明します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c9d7ce27-f5ad-4766-b9e9-34187da5bc24
ms.openlocfilehash: f78f8689e95fc1547f1a2b17c615592c00051f7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="type-extensions"></a><span data-ttu-id="8a3f8-104">型拡張</span><span class="sxs-lookup"><span data-stu-id="8a3f8-104">Type Extensions</span></span>

<span data-ttu-id="8a3f8-105">型拡張を使用すると、定義済みのオブジェクト型に新しいメンバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-105">Type extensions let you add new members to a previously defined object type.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a3f8-106">構文</span><span class="sxs-lookup"><span data-stu-id="8a3f8-106">Syntax</span></span>

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a><span data-ttu-id="8a3f8-107">コメント</span><span class="sxs-lookup"><span data-stu-id="8a3f8-107">Remarks</span></span>
<span data-ttu-id="8a3f8-108">型拡張には 2 つの形式があり、それぞれで構文と動作が若干異なります。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-108">There are two forms of type extensions that have slightly different syntax and behavior.</span></span> <span data-ttu-id="8a3f8-109">*固有拡張*は同じ名前空間またはモジュールで、同じソース ファイル、および同じアセンブリ (DLL または実行可能ファイル) に表示される、拡張対象の型とします。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-109">An *intrinsic extension* is an extension that appears in the same namespace or module, in the same source file, and in the same assembly (DLL or executable file) as the type being extended.</span></span> <span data-ttu-id="8a3f8-110">*省略可能な拡張*拡張で元のモジュール、名前空間、または拡張する型をアセンブリの外側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-110">An *optional extension* is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span> <span data-ttu-id="8a3f8-111">リフレクションで型をチェックするときは、その型に対して固有拡張が使用されますが、任意拡張は使用されません。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-111">Intrinsic extensions appear on the type when the type is examined by reflection, but optional extensions do not.</span></span> <span data-ttu-id="8a3f8-112">任意拡張はモジュール内で使用する必要があり、拡張を含むモジュールが開いている場合のスコープ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-112">Optional extensions must be in modules, and they are only in scope when the module that contains the extension is open.</span></span>

<span data-ttu-id="8a3f8-113">前の構文で*typename*拡張されている型を表します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-113">In the previous syntax, *typename* represents the type that is being extended.</span></span> <span data-ttu-id="8a3f8-114">アクセスできる型はいずれも拡張できますが、型の名前が、型略称ではなく、実際の型の名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-114">Any type that can be accessed can be extended, but the type name must be an actual type name, not a type abbreviation.</span></span> <span data-ttu-id="8a3f8-115">1 つの型拡張に複数のメンバーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-115">You can define multiple members in one type extension.</span></span> <span data-ttu-id="8a3f8-116">*自己識別子*通常のメンバーと同様、呼び出されるオブジェクトのインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-116">The *self-identifier* represents the instance of the object being invoked, just as in ordinary members.</span></span>

<span data-ttu-id="8a3f8-117">軽量構文では、`end` キーワードを省略できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-117">The `end` keyword is optional in lightweight syntax.</span></span>

<span data-ttu-id="8a3f8-118">型拡張で定義されたメンバーは、クラス型の他のメンバーと同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-118">Members defined in type extensions can be used just like other members on a class type.</span></span> <span data-ttu-id="8a3f8-119">他のメンバーと同様に、これらのメンバーは静的メンバーまたはインスタンス メンバーになることができます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-119">Like other members, they can be static or instance members.</span></span> <span data-ttu-id="8a3f8-120">これらのメソッドとも呼ばれます*拡張メソッド*; プロパティと呼ばれます*拡張機能プロパティ*のようにします。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-120">These methods are also known as *extension methods*; properties are known as *extension properties*, and so on.</span></span> <span data-ttu-id="8a3f8-121">任意拡張のメンバーはコンパイルされると、静的メンバーになります。このメンバーに対する最初のパラメーターとして、オブジェクト インスタンスが暗黙で渡されます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-121">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="8a3f8-122">ただし、これらのメンバーは、宣言された方法に応じてインスタンス メンバーまたは静的メンバーと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-122">However, they act as if they were instance members or static members according to how they are declared.</span></span> <span data-ttu-id="8a3f8-123">暗黙の拡張メンバーは型のメンバーとして含まれるため、無制限に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-123">Implicit extension members are included as members of the type and can be used without restriction.</span></span>

<span data-ttu-id="8a3f8-124">拡張メソッドは、仮想メソッドまたは抽象メソッドになることができません。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-124">Extension methods cannot be virtual or abstract methods.</span></span> <span data-ttu-id="8a3f8-125">拡張メソッドで同じ名前の他のメソッドをオーバーロードできますが、コンパイラは、あいまいな呼び出しの場合は非拡張メソッドを優先します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-125">They can overload other methods of the same name, but the compiler gives preference to non-extension methods in the case of an ambiguous call.</span></span>

<span data-ttu-id="8a3f8-126">1 つの型に対して複数の組み込み型拡張が存在する場合、すべてのメンバーが一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-126">If multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="8a3f8-127">オプション型拡張の場合は、1 つの型に対する複数の型拡張が存在する場合でも、各メンバーに同じ名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-127">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="8a3f8-128">クライアント コードで同じメンバー名が定義されている 2 つの異なるスコープを開いている場合にのみ、あいまいさに対するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-128">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

<span data-ttu-id="8a3f8-129">次の例では、モジュール内の型に対して組み込み型拡張を使用しています。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-129">In the following example, a type in a module has an intrinsic type extension.</span></span> <span data-ttu-id="8a3f8-130">モジュールの外部のクライアント コードでは、型の通常のメンバーとまったく同様に型拡張が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-130">To client code outside the module, the type extension appears as a regular member of the type in all respects.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

<span data-ttu-id="8a3f8-131">組み込み型拡張を使用すると、型の定義を複数のセクションに分割できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-131">You can use intrinsic type extensions to separate the definition of a type into sections.</span></span> <span data-ttu-id="8a3f8-132">この機能は、コンパイラが生成したコードとユーザーが作成したコードを別にしておく場合、複数のユーザーが作成したコードをグループ化する場合、複数の機能に関連付けられているコードをグループ化する場合など、大規模な型定義を管理する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-132">This can be useful in managing large type definitions, for example, to keep compiler-generated code and authored code separate or to group together code created by different people or associated with different functionality.</span></span>

<span data-ttu-id="8a3f8-133">次の例では、オプション型拡張を使用して `System.Int32` 型を拡張し、`FromString` 拡張メソッドで静的メンバーの `Parse` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-133">In the following example, an optional type extension extends the `System.Int32` type with an extension method `FromString` that calls the static member `Parse`.</span></span> <span data-ttu-id="8a3f8-134">`testFromString` メソッドで、新しいメンバーがインスタンス メンバーと同じように呼び出されているのがわかります。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-134">The `testFromString` method demonstrates that the new member is called just like any instance member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

<span data-ttu-id="8a3f8-135">IntelliSense で新しいインスタンス メンバーを `Int32` 型の他のメソッドと同じように使用できるのは、拡張を含むモジュールが開いている場合、または、拡張を含むモジュールは開いていないがスコープ内にある場合だけです。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-135">The new instance member will appear like any other method of the `Int32` type in IntelliSense, but only when the module that contains the extension is open or otherwise in scope.</span></span>

## <a name="generic-extension-methods"></a><span data-ttu-id="8a3f8-136">ジェネリック拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="8a3f8-136">Generic Extension Methods</span></span>
<span data-ttu-id="8a3f8-137">F# 3.1 で前に、f# コンパイラが (C#) の使用をサポートしていませんでした-ジェネリック型の変数、配列型、タプル型、または「この」パラメーターとして f# 関数型の拡張メソッドのスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-137">Before F# 3.1, the F# compiler didn't support the use of C#-style extension methods with a generic type variable, array type, tuple type, or an F# function type as the "this" parameter.</span></span> <span data-ttu-id="8a3f8-138">F# 3.1 ではこれらの拡張メンバーの使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-138">F# 3.1 supports the use of these extension members.</span></span>

<span data-ttu-id="8a3f8-139">たとえば、F# 3.1 コードでは、次の C# の構文に似ているシグネチャを使用する拡張メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-139">For example, in F# 3.1 code, you can use extension methods with signatures that resemble the following syntax in C#:</span></span>

```csharp
static member Method<T>(this T input, T other)
```

<span data-ttu-id="8a3f8-140">この方法はジェネリック型パラメーターが制約される場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-140">This approach is particularly useful when the generic type parameter is constrained.</span></span> <span data-ttu-id="8a3f8-141">さらに、F# コードでこのような拡張メンバーを宣言し、追加の、意味的に豊富な一連の拡張メソッドを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-141">Further, you can now declare extension members like this in F# code and define an additional, semantically rich set of extension methods.</span></span> <span data-ttu-id="8a3f8-142">F# では、通常、次の例に示すように拡張メンバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-142">In F#, you usually define extension members as the following example shows:</span></span>

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

<span data-ttu-id="8a3f8-143">ただし、ジェネリック型の場合、型変数は、制約されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-143">However, for a generic type, the type variable may not be constrained.</span></span> <span data-ttu-id="8a3f8-144">この制限を回避するために、F# で C# スタイル拡張メンバーを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-144">You can now declare a C#-style extension member in F# to work around this limitation.</span></span> <span data-ttu-id="8a3f8-145">この種の宣言と F# のインライン機能を組み合わせると、拡張機能メンバーとしてジェネリックなアルゴリズムを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-145">When you combine this kind of declaration with the inline feature of F#, you can present generic algorithms as extension members.</span></span>

<span data-ttu-id="8a3f8-146">次の宣言を検討します。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-146">Consider the following declaration:</span></span>

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="8a3f8-147">この宣言を使用すると、次の例のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-147">By using this declaration, you can write code that resembles the following sample.</span></span>

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

<span data-ttu-id="8a3f8-148">このコードでは、同じジェネリックな算術コードが単一の拡張メンバーを定義することによって、オーバーロードすることなく 2 種類のリストに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a3f8-148">In this code, the same generic arithmetic code is applied to lists of two types without overloading, by defining a single extension member.</span></span>


## <a name="see-also"></a><span data-ttu-id="8a3f8-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a3f8-149">See Also</span></span>
[<span data-ttu-id="8a3f8-150">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="8a3f8-150">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8a3f8-151">メンバー</span><span class="sxs-lookup"><span data-stu-id="8a3f8-151">Members</span></span>](members/index.md)