Return to [start here](../start%20here.md)

# Mapped Code

We have mapped some code to virtual memory. This page will be a living document as we figure out the general structure of the code. For now, everything has been split up into categories below:

# Table of Contents

[Global Functions](#Global%20Functions)
[UI Structures](#UI%20Structures)
[AI Structures](#AI%20Structures)
[Utility Structures](#Utility%20Structures)

# Global Functions

These are functions that don't seem to belong to a greater class.

- entry
- [main](../Mapped/main%20004CBDF6.md)
- [Other Global Functions](Global%20Functions.md)

# UI Structures:

These structures appear to manipulate the UI in some capacity.

- UIText
- UIButton
- UIGraph
- [ZTGameMgr](../Mapped/ZTGameMgr.md)
- ZTMiniMap
- ZTMessageQueue
- ZTMapView
- ZTMegatileMgr
- [[ZTMarketingMgr]]
- [[ZTResearchMgr]]
- ZTThoughtMgr
- [[ZTWorldMgr]]

# AI Structures

These structures might involve constant logic flow to control the game behavior.

- [[ZTHabitatMgr]]
- [[ZTAIMgr]]
- [[ZTScenarioMgr]]
- ZTShowMgr

# Utility Structures

The structures are more utility in nature.

- [[BFRegistry]]
- ZTScriptMgr
- BFResourceMgr
- [[ZTApp]]

# Unknown Structures

These structures are notable due to their connection to other mapped code, but their purpose hasn't been defined yet.

- [00635510](../Mapped/00635510.md)