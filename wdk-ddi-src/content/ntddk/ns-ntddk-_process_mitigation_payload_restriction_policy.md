---
UID: NS:ntddk._PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY
title: "_PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY"
author: windows-driver-content
description: Stores information about process mitigation policy.
old-location: kernel\process_mitigation_payload_restriction_policy.htm
old-project: kernel
ms.assetid: f55a47b2-c95c-4b6c-aeff-aed99dd9e43b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY, kernel.process_mitigation_payload_restriction_policy, PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY structure [Kernel-Mode Driver Architecture], PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY, *PPROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY, ntddk/PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY
product: Windows
targetos: Windows
req.typenames: PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY, *PPROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY
---

# _PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY structure


## -description


Stores information about process mitigation policy.


## -syntax


````
typedef struct _PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY {
  union {
    ULONG Flags;
    struct {
      ULONG EnableExportAddressFilter  :1;
      ULONG AuditExportAddressFilter  :1;
      ULONG EnableExportAddressFilterPlus  :1;
      ULONG AuditExportAddressFilterPlus  :1;
      ULONG EnableImportAddressFilter  :1;
      ULONG AuditImportAddressFilter  :1;
      ULONG EnableRopStackPivot  :1;
      ULONG AuditRopStackPivot  :1;
      ULONG EnableRopCallerCheck  :1;
      ULONG AuditRopCallerCheck  :1;
      ULONG EnableRopSimExec  :1;
      ULONG AuditRopSimExec  :1;
      ULONG ReservedFlags  :20;
    } DUMMYSTRUCTNAME;
  } DUMMYUNIONNAME;
} PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY, PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY;
````


## -struct-fields




### -field DUMMYUNIONNAME



### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME



### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EnableExportAddressFilter

If set this enables the Export Address Filter mitigation in enforcement mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditExportAddressFilter

If set this enables the Export Address Filter mitigation in audit mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EnableExportAddressFilterPlus

If set this enables the Export Address Filter Plus mitigation in enforcement mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditExportAddressFilterPlus

If set this enables the Export Address Filter mitigation in audit mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EnableImportAddressFilter

If set this enables the Import Address Filter mitigation in enforcement mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditImportAddressFilter

If set this enables the Import Address Filter mitigation in enforcement mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EnableRopStackPivot

If set this enables the stack pivot anti-ROP (Return-oriented-programming) mitigation in enforcement mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditRopStackPivot

If set this enables the stack pivot anti-ROP (Return-oriented-programming) mitigation in audit mode for the process.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EnableRopCallerCheck

If set this enables the caller check anti-ROP (Return-oriented-programming) mitigation in enforcement mode for the process. Applies to 32-bit processes only.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditRopCallerCheck

If set this enables the caller check anti-ROP (Return-oriented-programming) mitigation in audit mode for the process. Applies to 32-bit processes only.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EnableRopSimExec

If set this enables the simulated execution anti-ROP (Return-oriented-programming) mitigation in enforcement mode for the process. Applies to 32-bit processes only.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditRopSimExec

If set this enables the simulated execution anti-ROP (Return-oriented-programming) mitigation in audit mode for the process. Applies to 32-bit processes only.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ReservedFlags

Reserved.


### -field DUMMYUNIONNAME.Flags

Bitwise of flags in this structure.
