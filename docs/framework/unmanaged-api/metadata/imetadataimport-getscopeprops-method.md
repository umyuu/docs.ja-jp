---
title: "IMetaDataImport::GetScopeProps メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetScopeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b0936a9f47e2d0fa52816b78a7eecf3d244d594
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="e6fde-102">IMetaDataImport::GetScopeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="e6fde-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="e6fde-103">現在のメタデータ スコープにあるアセンブリまたはモジュールの名前、およびオプションでバージョン ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6fde-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6fde-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6fde-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6fde-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6fde-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e6fde-106">[out]アセンブリまたはモジュール名のバッファーです。</span><span class="sxs-lookup"><span data-stu-id="e6fde-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e6fde-107">[in]ワイド文字単位のサイズ`szName`です。</span><span class="sxs-lookup"><span data-stu-id="e6fde-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e6fde-108">[out]ワイド文字数で返される`szName`です。</span><span class="sxs-lookup"><span data-stu-id="e6fde-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="e6fde-109">[out, 省略可能]アセンブリまたはモジュールのバージョンを一意に識別する GUID を指すポインター。</span><span class="sxs-lookup"><span data-stu-id="e6fde-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6fde-110">コメント</span><span class="sxs-lookup"><span data-stu-id="e6fde-110">Remarks</span></span>  
 <span data-ttu-id="e6fde-111">[Imetadataemit::setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)メソッドを使用して、これらのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e6fde-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6fde-112">要件</span><span class="sxs-lookup"><span data-stu-id="e6fde-112">Requirements</span></span>  
 <span data-ttu-id="e6fde-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="e6fde-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6fde-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e6fde-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6fde-115">**ライブラリ:** MsCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6fde-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6fde-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6fde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6fde-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6fde-117">See Also</span></span>  
 [<span data-ttu-id="e6fde-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6fde-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e6fde-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6fde-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)