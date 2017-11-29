---
title: "アクセス制御 (F#)"
description: "型、メソッド、および f# のプログラミング言語では、関数などのプログラミング要素へのアクセスを制御する方法を説明します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a><span data-ttu-id="ae8dd-104">アクセス制御</span><span class="sxs-lookup"><span data-stu-id="ae8dd-104">Access Control</span></span>

<span data-ttu-id="ae8dd-105">*アクセス制御*型、メソッド、および関数など、特定のプログラム要素を使用できるクライアントの宣言を参照します。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-105">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="ae8dd-106">アクセス制御の基礎</span><span class="sxs-lookup"><span data-stu-id="ae8dd-106">Basics of Access Control</span></span>
<span data-ttu-id="ae8dd-107">F# でのアクセス制御指定子`public`、 `internal`、および`private`モジュール、型、メソッド、値の定義、関数、プロパティ、および明示的なフィールドに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-107">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="ae8dd-108">`public`すべての呼び出し元によってエンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-108">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="ae8dd-109">`internal`エンティティを同じアセンブリからのみアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-109">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="ae8dd-110">`private`外側の型またはモジュールからのみ、エンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-110">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="ae8dd-111">アクセス指定子`protected`が、許容可能な操作をサポートする言語で作成されたタイプを使用している場合、f# で使用されていない`protected`アクセスします。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-111">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="ae8dd-112">そのため、保護されたメソッドをオーバーライドする場合、メソッドが、クラスとそのサブフォルダー内でのみアクセス可能なします。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-112">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="ae8dd-113">場合を除き、エンティティの名前の前に、指定子を配置する一般に、`mutable`または`inline`指定子を使用すると、アクセス制御指定子の後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-113">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="ae8dd-114">アクセス指定子を使用していない場合、既定値は`public`、除く`let`は常に、型のバインディング`private`型にします。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-114">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="ae8dd-115">F# の署名は、f# のプログラム要素へのアクセスを制御するための別のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-115">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="ae8dd-116">署名は、アクセス制御の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-116">Signatures are not required for access control.</span></span> <span data-ttu-id="ae8dd-117">詳細については、「[シグネチャ](signatures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-117">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="ae8dd-118">アクセス制御のルール</span><span class="sxs-lookup"><span data-stu-id="ae8dd-118">Rules for Access Control</span></span>
<span data-ttu-id="ae8dd-119">アクセス制御では、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-119">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="ae8dd-120">継承の宣言 (の使用は、`inherit`クラスの基本クラスを指定する)、インターフェイスの宣言 (つまりには、クラスがインターフェイスを実装することを指定する)、および抽象メンバーが常に外側の型と同じのアクセシビリティを持ちます。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-120">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="ae8dd-121">そのため、これらのコンストラクトでアクセス制御指定子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-121">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="ae8dd-122">判別共用体の個々 のケースは、共用体の型から別の独自のアクセス制御修飾子にはできません。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-122">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="ae8dd-123">レコード型の個々 のフィールドは、レコードの種類から別の独自のアクセス制御修飾子にはできません。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-123">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="ae8dd-124">例</span><span class="sxs-lookup"><span data-stu-id="ae8dd-124">Example</span></span>
<span data-ttu-id="ae8dd-125">次のコードでは、アクセス制御指定子の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-125">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="ae8dd-126">プロジェクトで、2 つのファイルがある`Module1.fs`と`Module2.fs`です。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-126">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="ae8dd-127">各ファイルは、暗黙的にモジュールです。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-127">Each file is implicitly a module.</span></span> <span data-ttu-id="ae8dd-128">そのため、2 つのモジュールがある`Module1`と`Module2`です。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-128">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="ae8dd-129">プライベート型および内部の型がで定義されている`Module1`です。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-129">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="ae8dd-130">プライベート型にアクセスできません`Module2`、内部の型のことができます。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-130">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="ae8dd-131">次のコードで作成された型のアクセシビリティの確認`Module1.fs`です。</span><span class="sxs-lookup"><span data-stu-id="ae8dd-131">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="ae8dd-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae8dd-132">See Also</span></span>
[<span data-ttu-id="ae8dd-133">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ae8dd-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ae8dd-134">シグネチャ</span><span class="sxs-lookup"><span data-stu-id="ae8dd-134">Signatures</span></span>](signatures.md)