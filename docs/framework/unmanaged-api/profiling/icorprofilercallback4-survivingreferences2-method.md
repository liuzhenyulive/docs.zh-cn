---
title: "ICorProfilerCallback4::SurvivingReferences2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.SurvivingReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ced8542d2e84b6c317e20d7ff440e6c159383bfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="11ce6-102">ICorProfilerCallback4::SurvivingReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="11ce6-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="11ce6-103">将堆中对象的布局报告为非压缩垃圾回收的结果。</span><span class="sxs-lookup"><span data-stu-id="11ce6-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="11ce6-104">如果探查器已实现会调用此方法[ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="11ce6-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="11ce6-105">此回调可替换[icorprofilercallback2:: Survivingreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)方法，因为它能报告更大范围的长度超过 ULONG 中可表达新增功能的对象。</span><span class="sxs-lookup"><span data-stu-id="11ce6-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11ce6-106">语法</span><span class="sxs-lookup"><span data-stu-id="11ce6-106">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11ce6-107">参数</span><span class="sxs-lookup"><span data-stu-id="11ce6-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="11ce6-108">[in] 作为非压缩垃圾回收的结果而仍存在的连续对象块的数量。</span><span class="sxs-lookup"><span data-stu-id="11ce6-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="11ce6-109">即，`cSurvivingObjectIDRanges` 的值是 `objectIDRangeStart` 和 `cObjectIDRangeLength` 数组的大小，分别存储每个对象块的 `ObjectID` 和长度。</span><span class="sxs-lookup"><span data-stu-id="11ce6-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="11ce6-110">`SurvivingReferences2` 接来下的两个参数为并行数组。</span><span class="sxs-lookup"><span data-stu-id="11ce6-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="11ce6-111">即，`objectIDRangeStart` 和 `cObjectIDRangeLength` 涉及同一连续对象块。</span><span class="sxs-lookup"><span data-stu-id="11ce6-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="11ce6-112">[in] `ObjectID` 值的数组，其中每个值均为内存中连续活动对象块的起始地址。</span><span class="sxs-lookup"><span data-stu-id="11ce6-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="11ce6-113">[in] 整数数组，其中每个整数均为内存中保留下来的连续对象块的大小。</span><span class="sxs-lookup"><span data-stu-id="11ce6-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="11ce6-114">`objectIDRangeStart` 数组中引用的每个块均指定了大小。</span><span class="sxs-lookup"><span data-stu-id="11ce6-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11ce6-115">备注</span><span class="sxs-lookup"><span data-stu-id="11ce6-115">Remarks</span></span>  
 <span data-ttu-id="11ce6-116">应按以下方式解释 `objectIDRangeStart` 和 `cObjectIDRangeLength` 数组的元素，以确定垃圾回收后对象是否仍存在。</span><span class="sxs-lookup"><span data-stu-id="11ce6-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="11ce6-117">假定 `ObjectID` 值 (`ObjectID`) 在以下范围内：</span><span class="sxs-lookup"><span data-stu-id="11ce6-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="11ce6-118">对于以下范围内 `i` 的任何值，此对象在垃圾回收后仍存在：</span><span class="sxs-lookup"><span data-stu-id="11ce6-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="11ce6-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="11ce6-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="11ce6-120">非压缩垃圾回收将回收“死”对象占用的内存，但不会压缩释放的空间。</span><span class="sxs-lookup"><span data-stu-id="11ce6-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="11ce6-121">由此，内存返回到堆中，但“活”对象不会移动。</span><span class="sxs-lookup"><span data-stu-id="11ce6-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="11ce6-122">公共语言运行时 (CLR) 调用 `SurvivingReferences2` 进行非压缩垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="11ce6-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="11ce6-123">对于压缩垃圾回收， [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)改为调用。</span><span class="sxs-lookup"><span data-stu-id="11ce6-123">For compacting garbage collections, [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="11ce6-124">单个垃圾回收可针对一个生成进行压缩，而针对另一个生成不进行压缩。</span><span class="sxs-lookup"><span data-stu-id="11ce6-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="11ce6-125">对于任何特定代的垃圾回收，探查器会收到`SurvivingReferences2`回调或[MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)回调，但不是两个。</span><span class="sxs-lookup"><span data-stu-id="11ce6-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="11ce6-126">由于内部缓冲有限、服务器垃圾回收期间的多个回调以及其他原因，在特定的垃圾回收过程中，可能收到多个 `SurvivingReferences2` 回调。</span><span class="sxs-lookup"><span data-stu-id="11ce6-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="11ce6-127">如果在垃圾回收期间收到多个回调，则信息是累积的；所有 `SurvivingReferences2` 回调中报告的任何引用都将在垃圾回收后仍然存在。</span><span class="sxs-lookup"><span data-stu-id="11ce6-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="11ce6-128">如果探查器同时实现[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)和[ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)接口，`SurvivingReferences2`方法之前调用[ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)方法，但仅当`SurvivingReferences2`成功返回。</span><span class="sxs-lookup"><span data-stu-id="11ce6-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="11ce6-129">探查器可以返回一个 HRESULT，指示由 `SurvivingReferences2` 方法引发的故障，以避免调用第二种方法。</span><span class="sxs-lookup"><span data-stu-id="11ce6-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11ce6-130">要求</span><span class="sxs-lookup"><span data-stu-id="11ce6-130">Requirements</span></span>  
 <span data-ttu-id="11ce6-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11ce6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11ce6-132">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11ce6-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11ce6-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11ce6-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11ce6-134">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11ce6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ce6-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11ce6-135">See Also</span></span>  
 [<span data-ttu-id="11ce6-136">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="11ce6-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="11ce6-137">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="11ce6-137">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="11ce6-138">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="11ce6-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)