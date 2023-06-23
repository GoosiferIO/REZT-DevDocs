
Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md) / [[ZTApp]]

# ZTApp::updateGame

This is part of the main game loop. It appears to constantly update certain member functions.

# Table of Contents

[[#Decompile]]
[[#Connection to other Classes]]
[[#XREFs]]

# Decompile

Note about the code below: `GLOBAL_ZOO_BUDGET_STATUS` is the [[ZTGameMgr]] constructor pointer.

```Cpp
void __thiscall virt_meth_0x41a6d1(void *this)

{
  if ((*(char *)((int)this + 0x440) == '\0') && (*(char *)(GLOBAL_ZOO_BUDGET_STATUS + 1) != '\0')) {
    (**(code **)(*GLOBAL_ZOO_BUDGET_STATUS + 0x14))();
    (**(code **)(*DAT_00638098 + 8))();
    (**(code **)(*DAT_00638040 + 0x50))();
    (**(code **)(*DAT_00638ff8 + 0x20))();
    (**(code **)(*DAT_00639010 + 4))();
    (**(code **)(*DAT_00639000 + 4))();
  }
  return;
}
```

# Connection to other Classes

These member functions appear to be connected to the following classes:

- `GLOBAL_ZOO_BUDGET_STATUS` is [[ZTGameMgr]]
- [[ZTAIMgr]] ---> `00638098`
- [[ZTWorldMgr]] ---> `00638040`
- [[ZTScenarioMgr]] ---> `00638FF8`
- [[ZTResearchMgr]] ---> `00639010`
- [[ZTMarketingMgr]] ---> `00639000`

# XREFs

Only one reference to this function but it's not called from another function per se. This reference is its call from within the vtable it is a part of.

|Function Name|Function Location|Call Location|Access Type|Context|
|---|---|---|---|---|
||00630908 |00630990|(\*)| This is a virtual function table. | 
