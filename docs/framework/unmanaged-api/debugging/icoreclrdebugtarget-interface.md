---
title: "ICoreClrDebugTarget インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e13355078727a55c950bed795d3b01b6c7d52564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="439ff-102">ICoreClrDebugTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="439ff-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="439ff-103">参照カウントを制御し、プロセスを列挙し、Macintosh Silverlight にリモート ターゲットに接続されているデバッガーに関連付けられているメモリを解放するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="439ff-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="439ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="439ff-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="439ff-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="439ff-105">Methods</span></span>  
  
|<span data-ttu-id="439ff-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="439ff-106">Method</span></span>|<span data-ttu-id="439ff-107">説明</span><span class="sxs-lookup"><span data-stu-id="439ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="439ff-108">Icoreclrdebugtarget::enumprocesses メソッド</span><span class="sxs-lookup"><span data-stu-id="439ff-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="439ff-109">リモート コンピューターで実行されているプロセスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="439ff-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="439ff-110">Icoreclrdebugtarget::enumruntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="439ff-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="439ff-111">リモート コンピューターで、指定されたプロセスでは、共通言語ランタイム (Clr) を列挙します。</span><span class="sxs-lookup"><span data-stu-id="439ff-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="439ff-112">Icoreclrdebugtarget::freememory メソッド</span><span class="sxs-lookup"><span data-stu-id="439ff-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="439ff-113">このクラスの列挙体のメソッドによって割り当てられたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="439ff-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="439ff-114">コメント</span><span class="sxs-lookup"><span data-stu-id="439ff-114">Remarks</span></span>  
 <span data-ttu-id="439ff-115">現在、この機能はサポートされてのみリモート Macintosh コンピューターで実行されている Silverlight ベースのアプリケーションのターゲットをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="439ff-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="439ff-116">要件</span><span class="sxs-lookup"><span data-stu-id="439ff-116">Requirements</span></span>  
 <span data-ttu-id="439ff-117">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="439ff-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="439ff-118">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="439ff-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="439ff-119">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="439ff-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="439ff-120">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="439ff-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="439ff-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="439ff-121">See Also</span></span>  
 [<span data-ttu-id="439ff-122">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="439ff-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="439ff-123">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="439ff-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="439ff-124">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="439ff-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)