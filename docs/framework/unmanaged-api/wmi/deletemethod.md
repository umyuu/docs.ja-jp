---
title: "DeleteMethod 関数 (アンマネージ API リファレンス)"
description: "DeleteMethod 関数は、CIM クラス定義から、指定したメソッドを削除します。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: DeleteMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: DeleteMethod
helpviewer_keywords: DeleteMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d931cb76eeaf19ddeb80bdde412fabeea4b70203
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="deletemethod-function"></a><span data-ttu-id="4e4af-103">DeleteMethod 関数</span><span class="sxs-lookup"><span data-stu-id="4e4af-103">DeleteMethod function</span></span>
<span data-ttu-id="4e4af-104">CIM クラス定義から、指定したメソッドを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e4af-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4e4af-105">構文</span><span class="sxs-lookup"><span data-stu-id="4e4af-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4e4af-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e4af-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4e4af-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4e4af-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4e4af-108">[in]ポインター、 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4e4af-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="4e4af-109">[in]クラスのテーブルから削除するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="4e4af-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="4e4af-110">`wszName`有効なポインターである必要があります`LPCWSTR`です。</span><span class="sxs-lookup"><span data-stu-id="4e4af-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="4e4af-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e4af-111">Return value</span></span>

<span data-ttu-id="4e4af-112">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定義する定数として、コード。</span><span class="sxs-lookup"><span data-stu-id="4e4af-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4e4af-113">定数</span><span class="sxs-lookup"><span data-stu-id="4e4af-113">Constant</span></span>  |<span data-ttu-id="4e4af-114">値</span><span class="sxs-lookup"><span data-stu-id="4e4af-114">Value</span></span>  |<span data-ttu-id="4e4af-115">説明</span><span class="sxs-lookup"><span data-stu-id="4e4af-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="4e4af-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4e4af-116">0x80041002</span></span> | <span data-ttu-id="4e4af-117">指定されたメソッドが存在しません。</span><span class="sxs-lookup"><span data-stu-id="4e4af-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4e4af-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4e4af-118">0x80041006</span></span> | <span data-ttu-id="4e4af-119">操作を完了するのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="4e4af-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4e4af-120">0</span><span class="sxs-lookup"><span data-stu-id="4e4af-120">0</span></span> | <span data-ttu-id="4e4af-121">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="4e4af-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4e4af-122">コメント</span><span class="sxs-lookup"><span data-stu-id="4e4af-122">Remarks</span></span>

<span data-ttu-id="4e4af-123">この関数への呼び出しをラップする、 [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="4e4af-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="4e4af-124">メソッドの削除はサポートされていません[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM インスタンスを指すポインターです。</span><span class="sxs-lookup"><span data-stu-id="4e4af-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e4af-125">要件</span><span class="sxs-lookup"><span data-stu-id="4e4af-125">Requirements</span></span>  
 <span data-ttu-id="4e4af-126">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e4af-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e4af-127">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4e4af-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4e4af-128">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4e4af-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e4af-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e4af-129">See also</span></span>  
[<span data-ttu-id="4e4af-130">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4e4af-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)