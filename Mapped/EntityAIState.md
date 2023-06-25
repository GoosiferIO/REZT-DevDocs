Return to [start here](app://obsidian.md/start%20here.md) / [Mapped Code](app://obsidian.md/General/Mapped%20Code.md)

# `EntityAIState`

This class holds entity AI state, which it uses to call [[ZTAIMgr]]

The class exists at `4551cb`

# Table of Contents

[[#Structure]]
   [[#Member Functions]]

# Structure
## Data Members

The following offsets are added to the `*(0x638048)` pointer.

| Member |  Offset | Data Type | Member Type | Description | 
| ------- | --------------- | ---------| -----| ---- |
| mbr_0 | `0x0`  | unknown | unknown | First 3 are usually 0, sometimes an empty string or array|
| mbr_4 | `0x4`  | unknown | unknown ||
| mbr_8 | `0x8`  | unknown | unknown ||
| mbr_c | `0xc`  | ZT String | ptr | Point to start of string, eg fWalk|
| mbr_18 | `0x18`  | ZT Array[ZT String] | String Array | Array of input for mbr_c |
| mbr_24 | `0x24`  | int | unknown | Potentially seperate 4 bytes |
| mbr_28 | `0x28`  | ZT Array[ZT String] | String Array | AI queue |
| mbr_34 | `0x34`  | ZT String | ptr | mbr_c and mbr_18 combined|
| mbr_40 | `0x40`  | ZT String | ZT String | current behaviour? |
| mbr_4c | `0x4c`  | unknown | unknown | Usually 0 |
| mbr_50 | `0x50`  | int | ptr | Points to a specific guest/staff/animal AI class|
| mbr_54 | `0x54`  | int | ptr | unknown ptr|
| mbr_58 | `0x58`  | u8 | unknown ||
| mbr_59 | `0x59`  | u8 | unknown ||
| mbr_5a | `0x5a`  | u8 | unknown ||
| mbr_5b | `0x5b`  | u8 | unknown ||
| mbr_5c | `0x5c`  | u8 | unknown ||

## Member Functions

These are the documented functions part of this structure at this time.

|Member|Location|Ret Type|Member Type|Description|
|---|---|---|---|---|
|meth_0x435f0a|`0x435f0a`|void|member function|Calls [[ZTAIMgr]] cls_0x635324::virt_meth_0x436065 (inner class of ZTAIMgr) |