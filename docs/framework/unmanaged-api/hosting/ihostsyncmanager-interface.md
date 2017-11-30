---
title: "IHostSyncManager インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="39363-102">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39363-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="39363-103">共通言語ランタイム (CLR) に、Win32 の同期の関数を使用する代わりに、ホストを呼び出すことによって同期プリミティブを作成できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="39363-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39363-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-104">Methods</span></span>  
  
|<span data-ttu-id="39363-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-105">Method</span></span>|<span data-ttu-id="39363-106">説明</span><span class="sxs-lookup"><span data-stu-id="39363-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39363-107">CreateAutoEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="39363-108">自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="39363-109">CreateCrst メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="39363-110">同期のためのクリティカル セクション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="39363-111">CreateCrstWithSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="39363-112">同期用のスピン カウントをクリティカル セクション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="39363-113">CreateManualEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="39363-114">手動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="39363-115">CreateMonitorEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="39363-116">監視対象の自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="39363-117">CreateRWLockReaderEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="39363-118">リーダー ロックを実装するための手動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="39363-119">CreateRWLockWriterEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="39363-120">ライター ロックの実装の自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39363-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="39363-121">CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="39363-122">作成、 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)待機イベントのセマフォとして使用する CLR のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="39363-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="39363-123">SetCLRSyncManager メソッド</span><span class="sxs-lookup"><span data-stu-id="39363-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="39363-124">セット、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)に現在関連付けインスタンス`IHostSyncManager`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="39363-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39363-125">コメント</span><span class="sxs-lookup"><span data-stu-id="39363-125">Remarks</span></span>  
 <span data-ttu-id="39363-126">CLR のホストの実装を検出する`IHostSyncManager`を呼び出して、 [ihostcontrol::gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)メソッドを`IID`IID_IHostSyncManager のです。</span><span class="sxs-lookup"><span data-stu-id="39363-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39363-127">要件</span><span class="sxs-lookup"><span data-stu-id="39363-127">Requirements</span></span>  
 <span data-ttu-id="39363-128">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="39363-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39363-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39363-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39363-130">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="39363-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39363-131">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39363-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39363-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="39363-132">See Also</span></span>  
 [<span data-ttu-id="39363-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39363-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="39363-134">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39363-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)