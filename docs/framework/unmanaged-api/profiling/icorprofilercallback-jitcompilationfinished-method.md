---
title: "ICorProfilerCallback::JITCompilationFinished メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9719ce1474c2111692c6176655b75bd2d7edf923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="332e6-102">ICorProfilerCallback::JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="332e6-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="332e6-103">・ イン タイム (JIT) コンパイラが関数のコンパイルを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="332e6-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="332e6-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="332e6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="332e6-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="332e6-106">[in]コンパイルされた関数の ID。</span><span class="sxs-lookup"><span data-stu-id="332e6-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="332e6-107">[in]コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="332e6-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="332e6-108">[in]プロファイラーをブロックするかどうかを示す値は、ランタイムの動作に影響されます。</span><span class="sxs-lookup"><span data-stu-id="332e6-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="332e6-109">値が`true`ブロックにより、ランタイムでこのコールバックから戻るには、呼び出し元のスレッドを待機する場合は、それ以外の場合、`false`です。</span><span class="sxs-lookup"><span data-stu-id="332e6-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="332e6-110">値が`true`は妨げられませんが、ランタイム、プロファイルの結果の傾斜を実行できます。</span><span class="sxs-lookup"><span data-stu-id="332e6-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="332e6-111">要件</span><span class="sxs-lookup"><span data-stu-id="332e6-111">Requirements</span></span>  
 <span data-ttu-id="332e6-112">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="332e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="332e6-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="332e6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="332e6-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="332e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="332e6-115">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="332e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="332e6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="332e6-116">See Also</span></span>  
 [<span data-ttu-id="332e6-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="332e6-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="332e6-118">JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="332e6-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)