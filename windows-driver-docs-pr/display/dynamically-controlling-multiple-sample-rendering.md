---
title: Dynamically Controlling Multiple-Sample Rendering
description: Dynamically Controlling Multiple-Sample Rendering
ms.assetid: cd0bea22-29e8-40f7-987b-5c36765e5677
keywords: ["multiple-sample rendering WDK DirectX 9.0 , dynamic control", "rendering multisamples WDK DirectX 9.0 , dynamic control"]
---

# Dynamically Controlling Multiple-Sample Rendering


## <span id="ddk_dynamically_controlling_multiple_sample_rendering_gg"></span><span id="DDK_DYNAMICALLY_CONTROLLING_MULTIPLE_SAMPLE_RENDERING_GG"></span>


A DirectX 9.0 version driver can support the capability of alternately enabling and disabling multiple-sample rendering between the rendering of primitives. To report that the driver's device supports this capability, the driver sets the D3DPRASTERCAPS\_MULTISAMPLE\_TOGGLE capability bit in the **RasterCaps** member of the D3DCAPS9 structure. The driver returns a D3DCAPS9 structure in response to a **GetDriverInfo2** query similarly to how it returns a D3DCAPS8 structure as described in [Reporting DirectX 8.0 Style Direct3D Capabilities](reporting-directx-8-0-style-direct3d-capabilities.md). Support of this query is described in [Supporting GetDriverInfo2](supporting-getdriverinfo2.md).

To toggle multiple-sample rendering on and off between begin-scene and end-scene states, the driver receives the D3DDP2OP\_RENDERSTATE operation code in the [command stream](command-stream.md) of its [**D3dDrawPrimitives2**](https://msdn.microsoft.com/library/windows/hardware/ff544704) function. The driver processes the D3DRS\_MULTISAMPLEANTIALIAS render state from the **RenderState** member of the [**D3DHAL\_DP2RENDERSTATE**](https://msdn.microsoft.com/library/windows/hardware/ff545705) structure that is associated with this operation code. The driver determines whether to enable or disable multiple-sample rendering from the Boolean value in the **dwState** member of D3DHAL\_DP2RENDERSTATE. The value **TRUE** means to enable and **FALSE** means to disable.

If the D3DPRASTERCAPS\_MULTISAMPLE\_TOGGLE capability bit is set, the driver can receive the D3DRS\_MULTISAMPLEANTIALIAS render state between D3DRENDERSTATE\_SCENECAPTURE render states that specify **TRUE** for begin-scene information and **FALSE** for end-scene information.

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[display\display]:%20Dynamically%20Controlling%20Multiple-Sample%20Rendering%20%20RELEASE:%20%282/10/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



