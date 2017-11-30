---
title: "COR_PRF_MONITOR 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_MONITOR
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_MONITOR
helpviewer_keywords: COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type: apiref
caps.latest.revision: "33"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0e2f774bd178676494f24364c7b8890665c3810
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corprfmonitor-enumeration"></a><span data-ttu-id="5c822-102">COR_PRF_MONITOR 枚举</span><span class="sxs-lookup"><span data-stu-id="5c822-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="5c822-103">包含用于指定探查器希望订阅的行为、功能或事件的值。</span><span class="sxs-lookup"><span data-stu-id="5c822-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c822-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c822-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="5c822-105">成员</span><span class="sxs-lookup"><span data-stu-id="5c822-105">Members</span></span>  
 <span data-ttu-id="5c822-106">下面的部分列表`COR_PRF_MONITOR`按类别的枚举成员。</span><span class="sxs-lookup"><span data-stu-id="5c822-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="5c822-107">类别包括：</span><span class="sxs-lookup"><span data-stu-id="5c822-107">The categories are:</span></span>  
  
-   [<span data-ttu-id="5c822-108">设置任何标志</span><span class="sxs-lookup"><span data-stu-id="5c822-108">No flags set</span></span>](#None)  
  
-   [<span data-ttu-id="5c822-109">回调标志</span><span class="sxs-lookup"><span data-stu-id="5c822-109">Callback flags</span></span>](#Callback)  
  
-   [<span data-ttu-id="5c822-110">功能启用标志</span><span class="sxs-lookup"><span data-stu-id="5c822-110">Feature-enabling flags</span></span>](#Feature)  
  
-   [<span data-ttu-id="5c822-111">配置标志</span><span class="sxs-lookup"><span data-stu-id="5c822-111">Configuration flags</span></span>](#Config)  
  
-   [<span data-ttu-id="5c822-112">复合标志</span><span class="sxs-lookup"><span data-stu-id="5c822-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a><span data-ttu-id="5c822-113">设置任何标志</span><span class="sxs-lookup"><span data-stu-id="5c822-113">No flags set</span></span>  
  
|<span data-ttu-id="5c822-114">成员</span><span class="sxs-lookup"><span data-stu-id="5c822-114">Member</span></span>|<span data-ttu-id="5c822-115">描述</span><span class="sxs-lookup"><span data-stu-id="5c822-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="5c822-116">不设置任何标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a><span data-ttu-id="5c822-117">回调标志</span><span class="sxs-lookup"><span data-stu-id="5c822-117">Callback flags</span></span>  
  
|<span data-ttu-id="5c822-118">成员</span><span class="sxs-lookup"><span data-stu-id="5c822-118">Member</span></span>|<span data-ttu-id="5c822-119">描述</span><span class="sxs-lookup"><span data-stu-id="5c822-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="5c822-120">启用所有回调事件。</span><span class="sxs-lookup"><span data-stu-id="5c822-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="5c822-121">控件`AppDomainCreation*`和`AppDomainShutdown*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="5c822-122">控件`AssemblyLoad*`和`AssemblyUnload*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="5c822-123">控件`JITCachedFunctionSearch*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="5c822-124">此标志的行为在 .NET Framework 版本 2.0 中发生了变化。</span><span class="sxs-lookup"><span data-stu-id="5c822-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="5c822-125">控件`COMClassicVTable*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="5c822-126">控件`ClassLoad*`和`ClassUnload*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="5c822-127">控件`ExceptionCLRCatcher*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="5c822-128">控件[UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)和[ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口</span><span class="sxs-lookup"><span data-stu-id="5c822-128">Controls the [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="5c822-129">控件`FunctionEnter*`， `FunctionLeave*`，和`FunctionTailCall*`[分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="5c822-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="5c822-130">控件[ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)回调和`ExceptionSearch*`， `ExceptionOSHandler*`， `ExceptionUnwind*`，和`ExceptionCatcher*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-130">Controls the [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="5c822-131">控件[FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-131">Controls the [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="5c822-132">控件[GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)， [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)， [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)， [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)， [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)， [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)， [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)， [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)， [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)， [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)， [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)， [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)，和[FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)中的回调`ICorProfilerCallback*`接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-132">Controls the [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="5c822-133">控件`JITCompilation*`， [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)，和[JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-133">Controls the `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="5c822-134">控件`ModuleLoad*`， `ModuleUnload*`，和[ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-134">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="5c822-135">控件[ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-135">Controls the [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="5c822-136">控件`Remoting*`中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-136">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="5c822-137">控制 `Remoting*` 回调是否将监视异步事件。</span><span class="sxs-lookup"><span data-stu-id="5c822-137">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="5c822-138">控制是否向 `Remoting*` 回调传递 Cookie。</span><span class="sxs-lookup"><span data-stu-id="5c822-138">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="5c822-139">控件`RuntimeSuspend*`， `RuntimeResume*`， [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)，和[RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-139">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="5c822-140">控件[ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)， [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)， [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)，和[ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)中的回调[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)和[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5c822-140">Controls the [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a><span data-ttu-id="5c822-141">功能启用标志</span><span class="sxs-lookup"><span data-stu-id="5c822-141">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="5c822-142">成员</span><span class="sxs-lookup"><span data-stu-id="5c822-142">Member</span></span>|<span data-ttu-id="5c822-143">描述</span><span class="sxs-lookup"><span data-stu-id="5c822-143">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="5c822-144">允许检索的确切`ClassID`通过调用的泛型函数[GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法替换`COR_PRF_FRAME_INFO`返回值[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5c822-144">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="5c822-145">启用参数跟踪使用[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)回调或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)回调和[GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5c822-145">Enables argument tracing using the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback or the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="5c822-146">启用使用返回值跟踪[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调或[FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)回调和[GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5c822-146">Enables tracing of return values by using the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback or the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="5c822-147">已否决。</span><span class="sxs-lookup"><span data-stu-id="5c822-147">Deprecated.</span></span><br /><br /> <span data-ttu-id="5c822-148">不支持进程内调试。</span><span class="sxs-lookup"><span data-stu-id="5c822-148">In process debugging is not supported.</span></span> <span data-ttu-id="5c822-149">此标志无效。</span><span class="sxs-lookup"><span data-stu-id="5c822-149">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="5c822-150">已否决。</span><span class="sxs-lookup"><span data-stu-id="5c822-150">Deprecated.</span></span><br /><br /> <span data-ttu-id="5c822-151">允许探查器使用获取 IL 到本机代码的映射[GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)。</span><span class="sxs-lookup"><span data-stu-id="5c822-151">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="5c822-152">从 .NET Framework 2.0 开始，运行时始终跟踪从 IL 到本机代码的映射；因此，始终认为要设置此标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-152">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="5c822-153">通知运行时：探查器可能需要对象分配通知。</span><span class="sxs-lookup"><span data-stu-id="5c822-153">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="5c822-154">在初始化期间必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-154">This flag must be set during initialization.</span></span> <span data-ttu-id="5c822-155">它允许探查器随后使用`COR_PRF_MONITOR_OBJECT_ALLOCATED`标志接收[ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5c822-155">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="5c822-156">允许调用[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)和[RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5c822-156">Enables calls to the [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="5c822-157">探查器必须在启动时设置此标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-157">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="5c822-158">如果探查器指定此标志，它还必须指定 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`。</span><span class="sxs-lookup"><span data-stu-id="5c822-158">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="5c822-159">允许调用[DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5c822-159">Enables calls to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a><span data-ttu-id="5c822-160">配置标志</span><span class="sxs-lookup"><span data-stu-id="5c822-160">Configuration flags</span></span>  
  
|<span data-ttu-id="5c822-161">成员</span><span class="sxs-lookup"><span data-stu-id="5c822-161">Member</span></span>|<span data-ttu-id="5c822-162">描述</span><span class="sxs-lookup"><span data-stu-id="5c822-162">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="5c822-163">阻止所有本机映像（包括增强型探查器映像）进行加载。</span><span class="sxs-lookup"><span data-stu-id="5c822-163">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="5c822-164">如果此标志和 `COR_PRF_USE_PROFILE_IMAGES` 标志都已指定，将使用 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`。</span><span class="sxs-lookup"><span data-stu-id="5c822-164">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="5c822-165">禁用所有内联。</span><span class="sxs-lookup"><span data-stu-id="5c822-165">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="5c822-166">禁用所有代码优化。</span><span class="sxs-lookup"><span data-stu-id="5c822-166">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="5c822-167">禁用正常情况下在实时 (JIT) 编译和完全信任程序集类加载过程中完成的安全透明度检查。</span><span class="sxs-lookup"><span data-stu-id="5c822-167">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="5c822-168">这可以使某些检测更容易执行。</span><span class="sxs-lookup"><span data-stu-id="5c822-168">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="5c822-169">导致执行本机映像搜索，以查找增强型探查器映像。</span><span class="sxs-lookup"><span data-stu-id="5c822-169">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="5c822-170">对于给定程序集，如果找不到增强型探查器映像，则公共语言运行时将回退到该程序集的 JIT。</span><span class="sxs-lookup"><span data-stu-id="5c822-170">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="5c822-171">如果此标志和 `COR_PRF_DISABLE_ALL_NGEN_IMAGES` 标志都已指定，将使用 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`。</span><span class="sxs-lookup"><span data-stu-id="5c822-171">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a><span data-ttu-id="5c822-172">复合标志</span><span class="sxs-lookup"><span data-stu-id="5c822-172">Composite flags</span></span>  
  
|<span data-ttu-id="5c822-173">成员</span><span class="sxs-lookup"><span data-stu-id="5c822-173">Member</span></span>|<span data-ttu-id="5c822-174">描述</span><span class="sxs-lookup"><span data-stu-id="5c822-174">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="5c822-175">表示所有 `COR_PRF_MONITOR` 标志值。</span><span class="sxs-lookup"><span data-stu-id="5c822-175">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="5c822-176">表示可以在将探查器附加到运行中的应用之后进行设置的所有 `COR_PRF_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-176">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="5c822-177">语法部分指示此位掩码中存在的各个标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-177">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="5c822-178">启用所有回调事件。</span><span class="sxs-lookup"><span data-stu-id="5c822-178">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="5c822-179">表示只能在初始化过程中进行设置的所有 `COR_PRF_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-179">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="5c822-180">如果在初始化后尝试更改这些标志中的任一标志，则会返回一个指示失败的 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="5c822-180">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="5c822-181">表示需要配置增强的映像的所有 `COR_PRF_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="5c822-181">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c822-182">备注</span><span class="sxs-lookup"><span data-stu-id="5c822-182">Remarks</span></span>  
 <span data-ttu-id="5c822-183">A`COR_PRF_MONITOR`值用于[icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)和[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法以定义公共语言运行时向发出的事件通知探查器。</span><span class="sxs-lookup"><span data-stu-id="5c822-183">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c822-184">要求</span><span class="sxs-lookup"><span data-stu-id="5c822-184">Requirements</span></span>  
 <span data-ttu-id="5c822-185">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c822-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c822-186">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c822-186">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c822-187">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c822-187">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c822-188">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c822-188">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c822-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c822-189">See Also</span></span>  
 [<span data-ttu-id="5c822-190">分析枚举</span><span class="sxs-lookup"><span data-stu-id="5c822-190">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [<span data-ttu-id="5c822-191">GetEventMask 方法</span><span class="sxs-lookup"><span data-stu-id="5c822-191">GetEventMask Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
 [<span data-ttu-id="5c822-192">SetEventMask 方法</span><span class="sxs-lookup"><span data-stu-id="5c822-192">SetEventMask Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)