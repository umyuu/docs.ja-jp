---
title: ICorDebugModuleBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint
helpviewer_keywords: ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e3937c6c0baef4cc927b5c5d789826c70beebf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="f4b5d-102">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="f4b5d-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="f4b5d-103">特定のモジュールへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f4b5d-103">Provides access to specific modules.</span></span> <span data-ttu-id="f4b5d-104">このインターフェイスは、ICorDebugBreakpoint インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="f4b5d-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4b5d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f4b5d-105">Methods</span></span>  
  
|<span data-ttu-id="f4b5d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="f4b5d-106">Method</span></span>|<span data-ttu-id="f4b5d-107">説明</span><span class="sxs-lookup"><span data-stu-id="f4b5d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4b5d-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="f4b5d-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="f4b5d-109">このブレークポイントが設定されているモジュールを参照する ICorDebugModule へのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f4b5d-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4b5d-110">コメント</span><span class="sxs-lookup"><span data-stu-id="f4b5d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4b5d-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f4b5d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4b5d-112">要件</span><span class="sxs-lookup"><span data-stu-id="f4b5d-112">Requirements</span></span>  
 <span data-ttu-id="f4b5d-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="f4b5d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4b5d-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4b5d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4b5d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4b5d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4b5d-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4b5d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b5d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4b5d-117">See Also</span></span>  
 [<span data-ttu-id="f4b5d-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4b5d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)