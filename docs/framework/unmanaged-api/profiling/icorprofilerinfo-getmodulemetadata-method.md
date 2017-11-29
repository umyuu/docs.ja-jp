---
title: "ICorProfilerInfo::GetModuleMetaData メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 540ed6f1f84f096563aa94798090c3511d6db5d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="9776d-102">ICorProfilerInfo::GetModuleMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="9776d-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="9776d-103">指定したモジュールにマップされるメタデータ インターフェイスのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9776d-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9776d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9776d-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9776d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9776d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9776d-106">[in]インターフェイスのインスタンスをマップするモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="9776d-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="9776d-107">[in]値、 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)マニフェスト ファイルを開くためのモードを指定する列挙です。</span><span class="sxs-lookup"><span data-stu-id="9776d-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="9776d-108">のみ、 `ofRead`、`ofWrite`と`ofNoTransform`のビットが無効です。</span><span class="sxs-lookup"><span data-stu-id="9776d-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="9776d-109">[in]インスタンスが取得するメタデータ インターフェイスの ID (GUID) の参照。</span><span class="sxs-lookup"><span data-stu-id="9776d-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="9776d-110">参照してください[メタデータ インターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)インターフェイスの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="9776d-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="9776d-111">[out]メタデータ インターフェイスのインスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9776d-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9776d-112">コメント</span><span class="sxs-lookup"><span data-stu-id="9776d-112">Remarks</span></span>  
 <span data-ttu-id="9776d-113">読み取り/書き込みモードで開かれるメタデータを要求することがありますが、プログラムのメタデータ実行の速度が遅くなります、コンパイラから場合と同様に、メタデータを最適化することはできませんに変更が行われるためです。</span><span class="sxs-lookup"><span data-stu-id="9776d-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="9776d-114">メタデータを所有している (リソースのモジュール) などの一部のモジュールはありません。</span><span class="sxs-lookup"><span data-stu-id="9776d-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="9776d-115">ような場合、 `GetModuleMetaData` S_FALSE とに null 値の HRESULT 値を返す *`ppOut`です。</span><span class="sxs-lookup"><span data-stu-id="9776d-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9776d-116">要件</span><span class="sxs-lookup"><span data-stu-id="9776d-116">Requirements</span></span>  
 <span data-ttu-id="9776d-117">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="9776d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9776d-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9776d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9776d-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9776d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9776d-120">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9776d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9776d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9776d-121">See Also</span></span>  
 [<span data-ttu-id="9776d-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9776d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)