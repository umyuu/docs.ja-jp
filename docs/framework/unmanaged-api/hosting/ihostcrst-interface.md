---
title: "IHostCrst インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="21478-102">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21478-102">IHostCrst Interface</span></span>
<span data-ttu-id="21478-103">スレッド処理の重要なセクションのホストの表現として機能します。</span><span class="sxs-lookup"><span data-stu-id="21478-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21478-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="21478-104">Methods</span></span>  
  
|<span data-ttu-id="21478-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="21478-105">Method</span></span>|<span data-ttu-id="21478-106">説明</span><span class="sxs-lookup"><span data-stu-id="21478-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21478-107">Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="21478-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="21478-108">クリティカル セクションに入ります。</span><span class="sxs-lookup"><span data-stu-id="21478-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="21478-109">Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="21478-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="21478-110">クリティカル セクションのままにします。</span><span class="sxs-lookup"><span data-stu-id="21478-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="21478-111">SetSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="21478-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="21478-112">クリティカル セクションのスピン カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="21478-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="21478-113">TryEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="21478-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="21478-114">クリティカル セクション、およびレポートの成功または失敗をすぐに入力しようとしています。</span><span class="sxs-lookup"><span data-stu-id="21478-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21478-115">コメント</span><span class="sxs-lookup"><span data-stu-id="21478-115">Remarks</span></span>  
 <span data-ttu-id="21478-116">`IHostCrst`などを使用して Win32 関数ではなく、共通言語ランタイム (CLR)、クリティカル セクションのホストの表現と直接通信するためには、`EnterCriticalSection`または`LeaveCriticalSection`です。</span><span class="sxs-lookup"><span data-stu-id="21478-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21478-117">要件</span><span class="sxs-lookup"><span data-stu-id="21478-117">Requirements</span></span>  
 <span data-ttu-id="21478-118">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="21478-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21478-119">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21478-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21478-120">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="21478-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21478-121">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21478-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21478-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="21478-122">See Also</span></span>  
 [<span data-ttu-id="21478-123">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21478-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="21478-124">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21478-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="21478-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21478-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)