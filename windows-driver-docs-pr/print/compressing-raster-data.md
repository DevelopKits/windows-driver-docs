---
title: Compressing Raster Data
author: windows-driver-content
description: Compressing Raster Data
ms.assetid: 8c74e7f3-5601-4510-9fcd-261f5cd48e9c
keywords:
- Unidrv, raster data compression
- GPD files WDK Unidrv , raster data compression
- raster data compression WDK Unidrv
- compressing raster data WDK Unidrv
- Unidrv WDK print
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Compressing Raster Data


## <a href="" id="ddk-compressing-raster-data-gg"></a>


Unidrv supports raster data compression using the following three formats:

-   Tagged Image File Format (TIFF), version 4.0

-   Delta-Row Compression (DRC)

-   East Asian Run-Length Encoding (FE-RLE)

These methods are defined in the *HP PCL 5 Printer Language Technical Reference*. (This resource may not be available in some languages and countries.)

You can include entries in a GPD file to indicate which of these compression formats your printer supports. You can also provide your own compression algorithm.

For more information about raster data compression, see the following topics:

[Using Unidrv-Supported Compression](using-unidrv-supported-compression.md)

[Using Customized Compression](using-customized-compression.md)

 

 




