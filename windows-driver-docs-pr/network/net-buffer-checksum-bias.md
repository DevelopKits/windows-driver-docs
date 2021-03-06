---
title: NET_BUFFER_CHECKSUM_BIAS macro
author: windows-driver-content
description: NET_BUFFER_CHECKSUM_BIAS is a macro that NDIS drivers use to get the ChecksumBias member of a NET_BUFFER structure.
ms.assetid: 8fd4aafc-c095-4026-8c6b-8f739e429285
ms.author: windowsdriverdev 
ms.date: 07/18/2017 
ms.topic: article 
ms.prod: windows-hardware 
ms.technology: windows-devices 
keywords:
 - NET_BUFFER_CHECKSUM_BIAS macro Network Drivers Starting with Windows Vista
---

# NET\_BUFFER\_CHECKSUM\_BIAS macro


NET\_BUFFER\_CHECKSUM\_BIAS is a macro that NDIS drivers use to get the **ChecksumBias** member of a [**NET\_BUFFER**](https://msdn.microsoft.com/library/windows/hardware/ff568376) structure.

Syntax
------

```ManagedCPlusPlus
USHORT NET_BUFFER_CHECKSUM_BIAS(
   PNET_BUFFER _NB
);
```

Parameters
----------

*\_NB*   
A pointer to a NET\_BUFFER structure.

Return value
------------

NET\_BUFFER\_CHECKSUM\_BIAS returns the value of the **ChecksumBias** member of the indicated NET\_BUFFER structure.

Remarks
-------

The return value specifies the number of bytes of data to skip over at the beginning of the data buffer when computing a checksum. This value is used by the TCP/IP protocol.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Target platform</p></td>
<td>[Universal](http://go.microsoft.com/fwlink/p/?linkid=531356)</td>
</tr>
<tr class="even">
<td><p>Version</p></td>
<td><p>Supported in NDIS 6.0 and later.</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Ndis.h (include Ndis.h)</td>
</tr>
</tbody>
</table>

## See also


[**NET\_BUFFER**](https://msdn.microsoft.com/library/windows/hardware/ff568376)

 

 




