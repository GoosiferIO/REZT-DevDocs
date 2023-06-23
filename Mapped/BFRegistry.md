Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md)

# `BFRegistry`

This structure seems to be a mapping between class names as strings and some constructor functions. Notably, it looks to be creating relationships between the string names of a class and the pointer to that class. Below is a table that connects some of these relationships:

| Class Name | Init Function | Class Address |
| ------- | -------- | ---------- |
| [[ZTApp]] | | 0x00638148 |
| DX8SndMgr | 0x5280c3 | 0x630a48 |
| [[ZTGameMgr]] | 0x527dc7 | 0x00638048 | 
| [[ZTAIMgr]] | 0x525961 | 0x63536c | 
| ZTScenarioMgr | 0x525e27 | 0x630d7c |
| ZTMarketingMgr | 0x5257e7 | 0x635110 | 
| ZTAdvTerrainMgr | 0x525470 | 0x630ad8 |
| ZTHabitatMgr | 0x464925 | 0x463737 |
| ZTMegatileMgr | 0x463e1e | 0x6355c4 |
| ZTThoughtMgr | 0x464b34 | 0x6355cc |
| [[ZTWorldMgr]] | 0x46498e | 0x630cac |
| ZTScriptMgr | 0x51e0d6 | 0x6358c8 |
| [[ZTResearchMgr]] | 0x51e293 | 0x635100 |
| ZTShowMgr | 0x51f79e | 0x635120 |
| UILayout | 0x50fa37 | ---- |
| UIEditableText | 0x510c52 | ---- |
| UIImage | 0x50ffd8 | ---- |
| UIButton | 0x50f8b0 | ---- |
| UIText | 0x510a49 | ---- |
| UIStatusImage | 0x510f33 | ---- |
| UIScrollBar | 0x5111cb | ---- |
| UIListBox | 0x511357 | ---- |
| UIRadioSet | 0x5114fb | ---- |
| UIImageSet | 0x512275 | ---- | 
| UIScrollingRegion | 0x5125d8 | ---- | 
| ZTMiniMap | 0x520d1c | 0x6313e4 |
| ZTMapView | 0x5205bc | 0x6358a8 |
| ZTMessageQueue | 0x520b61 | 0x631e94 |
| UIGraph | 0x51a7c3 | ---- |
