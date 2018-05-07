---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastUnlockAllByKey
title: FsRtlFastUnlockAllByKey function
author: windows-driver-content
description: The FsRtlFastUnlockAllByKey routine releases all byte-range locks that were acquired by the specified process, with the specified key value, for a file.
old-location: ifsk\fsrtlfastunlockallbykey.htm
old-project: ifsk
ms.assetid: 57214e6a-cd29-4576-894a-9523ca3c7e7d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlFastUnlockAllByKey, FsRtlFastUnlockAllByKey routine [Installable File System Drivers], fsrtlref_193afe01-52f3-4dbc-8a33-bd058beb10ce.xml, ifsk.fsrtlfastunlockallbykey, ntifs/FsRtlFastUnlockAllByKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlFastUnlockAllByKey
product: Windows
targetos: Windows
req.typenames: 
---

# FsRtlFastUnlockAllByKey function


## -description


The <b>FsRtlFastUnlockAllByKey</b> routine releases all byte-range locks that were acquired by the specified process, with the specified key value, for a file. 


## -parameters




### -param FileLock [in]

A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


### -param FileObject [in]

A pointer to the file object for the file.


### -param ProcessId [in]

A pointer to the process ID for the process.


### -param Key [in]

The key value.


### -param Context [in, optional]

Optional context pointer to be used when completing IRPs. 


## -returns



<b>FsRtlFastUnlockAllByKey</b> returns STATUS_SUCCESS or an error status code such as STATUS_RANGE_NOT_LOCKED. 




## -remarks



After releasing the byte-range locks, <b>FsRtlFastUnlockAllByKey</b> completes any currently queued lock IRPs that can now be completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>
 

 
