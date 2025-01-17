---
UID: NS:wlanihv._DOT11EXT_IHV_CONNECTIVITY_PROFILE
title: _DOT11EXT_IHV_CONNECTIVITY_PROFILE (wlanihv.h)
description: The DOT11EXT_IHV_CONNECTIVITY_PROFILE structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11ext_ihv_connectivity_profile.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11EXT_IHV_CONNECTIVITY_PROFILE structure"]
ms.keywords: "*PDOT11EXT_IHV_CONNECTIVITY_PROFILE, DOT11EXT_IHV_CONNECTIVITY_PROFILE, DOT11EXT_IHV_CONNECTIVITY_PROFILE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_a0d8e30b-4a72-44d2-a83a-c7b1785f2c8e.xml, PDOT11EXT_IHV_CONNECTIVITY_PROFILE, PDOT11EXT_IHV_CONNECTIVITY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_CONNECTIVITY_PROFILE, netvista.dot11ext_ihv_connectivity_profile, wlanihv/DOT11EXT_IHV_CONNECTIVITY_PROFILE, wlanihv/PDOT11EXT_IHV_CONNECTIVITY_PROFILE"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: DOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11EXT_IHV_CONNECTIVITY_PROFILE
 - wlanihv/_DOT11EXT_IHV_CONNECTIVITY_PROFILE
 - PDOT11EXT_IHV_CONNECTIVITY_PROFILE
 - wlanihv/PDOT11EXT_IHV_CONNECTIVITY_PROFILE
 - DOT11EXT_IHV_CONNECTIVITY_PROFILE
 - wlanihv/DOT11EXT_IHV_CONNECTIVITY_PROFILE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihv.h
api_name:
 - _DOT11EXT_IHV_CONNECTIVITY_PROFILE
 - PDOT11EXT_IHV_CONNECTIVITY_PROFILE
 - DOT11EXT_IHV_CONNECTIVITY_PROFILE
---

# _DOT11EXT_IHV_CONNECTIVITY_PROFILE structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_CONNECTIVITY_PROFILE structure specifies connectivity settings for the IHV
  profile.

## -struct-fields

### -field pszXmlFragmentIhvConnectivity

A pointer to the string that defines the IHV connectivity profile.

## -syntax

```cpp
typedef struct _DOT11EXT_IHV_CONNECTIVITY_PROFILE {
  LPWSTR pszXmlFragmentIhvConnectivity;
} DOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE;
```

