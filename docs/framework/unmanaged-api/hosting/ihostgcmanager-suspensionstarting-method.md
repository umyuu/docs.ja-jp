---
title: "IHostGCManager::SuspensionStarting メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c807a124570f38922509d27e52936b980e36fba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="01324-102">IHostGCManager::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="01324-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="01324-103">共通言語ランタイム (CLR) がガベージ コレクションを実行する、タスクの実行を中断していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="01324-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01324-104">構文</span><span class="sxs-lookup"><span data-stu-id="01324-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="01324-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="01324-105">Return Value</span></span>  
  
|<span data-ttu-id="01324-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01324-106">HRESULT</span></span>|<span data-ttu-id="01324-107">説明</span><span class="sxs-lookup"><span data-stu-id="01324-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01324-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="01324-108">S_OK</span></span>|<span data-ttu-id="01324-109">`SuspensionStarting`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="01324-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="01324-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01324-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01324-111">CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="01324-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01324-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01324-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01324-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="01324-113">The call timed out.</span></span>|  
|<span data-ttu-id="01324-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01324-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01324-115">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="01324-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01324-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01324-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01324-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="01324-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01324-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01324-118">E_FAIL</span></span>|<span data-ttu-id="01324-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="01324-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01324-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="01324-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01324-121">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="01324-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01324-122">コメント</span><span class="sxs-lookup"><span data-stu-id="01324-122">Remarks</span></span>  
 <span data-ttu-id="01324-123">CLR 呼び出し`SuspensionStarting`ガベージ コレクションが発生しているホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="01324-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01324-124">このタスクのスケジュールを変更できません。</span><span class="sxs-lookup"><span data-stu-id="01324-124">Do not reschedule this task.</span></span> <span data-ttu-id="01324-125">タスクのスケジュールを変更する必要があります、ホストと[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)と呼びます。</span><span class="sxs-lookup"><span data-stu-id="01324-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01324-126">要件</span><span class="sxs-lookup"><span data-stu-id="01324-126">Requirements</span></span>  
 <span data-ttu-id="01324-127">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="01324-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01324-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01324-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01324-129">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="01324-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01324-130">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01324-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01324-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="01324-131">See Also</span></span>  
 [<span data-ttu-id="01324-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01324-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="01324-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01324-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="01324-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01324-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="01324-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01324-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="01324-136">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01324-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)