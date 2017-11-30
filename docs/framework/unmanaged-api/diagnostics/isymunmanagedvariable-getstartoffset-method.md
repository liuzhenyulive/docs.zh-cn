---
title: "ISymUnmanagedVariable::GetStartOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetStartOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b7fd3a64202224ef5a7cc348ee8e9974a664d09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="0da50-102">ISymUnmanagedVariable::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0da50-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="0da50-103">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="0da50-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="0da50-104">如果这是一个作用域内的局部变量，起始偏移量将位于内定义的范围的偏移量。</span><span class="sxs-lookup"><span data-stu-id="0da50-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da50-105">语法</span><span class="sxs-lookup"><span data-stu-id="0da50-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0da50-106">参数</span><span class="sxs-lookup"><span data-stu-id="0da50-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0da50-107">[out]指向的指针`ULONG32`接收的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="0da50-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0da50-108">返回值</span><span class="sxs-lookup"><span data-stu-id="0da50-108">Return Value</span></span>  
 <span data-ttu-id="0da50-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="0da50-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da50-110">要求</span><span class="sxs-lookup"><span data-stu-id="0da50-110">Requirements</span></span>  
 <span data-ttu-id="0da50-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0da50-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da50-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0da50-112">See Also</span></span>  
 [<span data-ttu-id="0da50-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="0da50-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="0da50-114">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0da50-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)