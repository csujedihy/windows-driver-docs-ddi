---
UID: NC:d3d10umddi.PFND3DWDDM2_4DDI_NEGOTIATECRYPTOSESSIONKEYEXCHANGE
title: PFND3DWDDM2_4DDI_NEGOTIATECRYPTOSESSIONKEYEXCHANGE
author: windows-driver-content
description:
ms.assetid: 29deaace-55a0-406e-949e-c3aca2b8097c
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d10umddi.h
req.include-header: S3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	PFND3DWDDM2_4DDI_NEGOTIATECRYPTOSESSIONKEYEXCHANGE
product: Windows
targetos: Windows
---

# PFND3DWDDM2_4DDI_NEGOTIATECRYPTOSESSIONKEYEXCHANGE callback function

## -description

Establishes a session key for a cryptographic session object.

## -prototype

```
//Declaration

PFND3DWDDM2_4DDI_NEGOTIATECRYPTOSESSIONKEYEXCHANGE Pfnd3dwddm24DdiNegotiatecryptosessionkeyexchange;

// Definition

HRESULT Pfnd3dwddm24DdiNegotiatecryptosessionkeyexchange
(
	D3D10DDI_HDEVICE hDevice
	D3D11_1DDI_HCRYPTOSESSION hCryptoSession
	D3DWDDM2_4DDI_CRYPTO_SESSION_KEY_EXCHANGE_FLAGS flags
	UINT DataSize
	BYTE *pData
)
{...}

PFND3DWDDM2_4DDI_NEGOTIATECRYPTOSESSIONKEYEXCHANGE


```

## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).

### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to CreateCryptoSession.

### -param flags [in]

The flag value for the function.

### -param DataSize [in]

The size, in bytes, of the data that the pData member points to.

### -param *pData [in, out]

A pointer to a buffer that contains the encrypted session key.

## -returns

Returns one of the following HRESULT values:

| Return code | Description |
|---|---|
|S_OK|The session key for the cryptographic session was negotiated successfully.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The *pData* parameter references a buffer that contains a session key for the cryptographic session. The key exchange mechanism depends on the type of the encryption algorithm that is used by the cryptographic session.

For sessions that use the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm, the key buffer must contain 256 bytes of data and must be encrypted by using the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm with the public key from the cryptographic session certificate.

The key exchange for a cryptographic session is identical to the key exchange for the Output Protection Manager (OPM) interface. However, the OPM key buffer contains additional data besides the session key.

>**Note**  The same certificate can be used for the cryptographic session and OPM session key.


## -see-also