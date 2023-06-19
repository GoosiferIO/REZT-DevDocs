# `ZTGameMgr::subtractToBudget(float deposit)`

Located at `0x0041EF68` and is part of the [ZTGameMgr](ZTGameMgr.md) class.

This function subtracts from the budget. Like [addToBudget](ZTGameMgr%20addToBudget.md), this one also calls [0x0040EE3D](ZTGameMgr%200x0040EE3D.md) from within. Its purpose is still unclear.

A rough decompile from Ghidra can be observed below:

```C++
void __thiscall OOAnalyzer::cls_0x40f018::meth_0x41ef68(cls_0x40f018 *this,float param_1)

{
  *(float *)&this->field_0xc = *(float *)&this->field_0xc - param_1;
  FUN_0040ee3d();
  return;
}
```