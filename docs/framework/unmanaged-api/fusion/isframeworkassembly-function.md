---
title: "IsFrameworkAssembly 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IsFrameworkAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IsFrameworkAssembly
helpviewer_keywords: IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 216a7221550cb6345b29b5ed9e45b13ce40eadf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="ef8a6-102">IsFrameworkAssembly 関数</span><span class="sxs-lookup"><span data-stu-id="ef8a6-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="ef8a6-103">指定したアセンブリが管理されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef8a6-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef8a6-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef8a6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef8a6-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="ef8a6-106">[in]チェック対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="ef8a6-107">[out]アセンブリが管理されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="ef8a6-108">[in]アセンブリの一意の id を表す uncanonicalized 文字列。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="ef8a6-109">[入力] `pwzFrameworkAssemblyIdentity` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef8a6-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ef8a6-110">Remarks</span></span>  
 <span data-ttu-id="ef8a6-111">`pwzAssemblyReference`パラメーターは、アセンブリの名前を含む文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="ef8a6-112">このアセンブリが .NET Framework の一部である場合、`pbIsFrameworkAssembly`パラメーターはブール値を含める`true`です。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="ef8a6-113">名前付きのアセンブリが .NET Framework の一部ではない場合、または場合、`pwzAssemblyReference`パラメーターでは、アセンブリを指定しない場合`pbIsFrameworkAssembly`のブール値を含む`false`です。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef8a6-114">要件</span><span class="sxs-lookup"><span data-stu-id="ef8a6-114">Requirements</span></span>  
 <span data-ttu-id="ef8a6-115">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef8a6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8a6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef8a6-116">See Also</span></span>  
 [<span data-ttu-id="ef8a6-117">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="ef8a6-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)