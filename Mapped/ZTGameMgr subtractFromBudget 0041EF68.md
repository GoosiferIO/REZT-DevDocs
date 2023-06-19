Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md) / [ZTGameMgr](ZTGameMgr.md)

# `ZTGameMgr::subtractToBudget(float deposit)`

Located at `0x0041EF68` and is part of the [ZTGameMgr](ZTGameMgr.md) class.

This function subtracts from the budget. Like [ZTGameMgr::addToBudget](ZTGameMgr%20addToBudget%200040F018.md), this one also calls [ZTGameMgr::0x0040EE3D](ZTGameMgr%200040EE3D.md) from within. Its purpose is still unclear.

# Table of Contents

[Decompile](#Decompile)
[XREFs](#XREFs)

# Decompile

A rough decompile from Ghidra can be observed below:

```C++
void __thiscall OOAnalyzer::cls_0x40f018::meth_0x41ef68(cls_0x40f018 *this,float param_1)

{
  *(float *)&this->field_0xc = *(float *)&this->field_0xc - param_1;
  FUN_0040ee3d();
  return;
}
```

# XREFs

All locations where this function is called. None of these have yet been explored.

| Function Name | Function Location | Call Location | Access Type | Context |
| ---- | ---- | ---- | ---- | ---- |
| | 0041F1BA | 0041F284 | (c) | |
| | 0041F2AE | 0041F304 | (c) | |
| | 004691CD | 00469281 | (c) | |
| | 0046937E | 0046944C | (c) | |
| | 00470261 | 004702E3 | (c) | Virtual method |
| | 004D8533 | 0047C043 | (c) | Virtual method |
| | 00483F11 | 004841A3 | (c) | |
| | 00483F11 | 00484230 | (c) | |
| | 004DA252 | 00488E9D | (c) | Virtual method |
| | 00486FCD | 0048A021 | (c) | Virtual method |
| | 0048F624 | 0048F76C | (c) | Virtual method |
| | 0049BEC7 | 0049BEFE | (c) | |
| | 004F94BE | 004A099A | (c) | |
| | 004868CF | 004D8EDA | (c) | |
| | 005B6710 | 004DEB1B | (c) | |
| | 004F94BE | 004EFD66 | (c) | |
| | 004F94BE | 005CE004 | (c) | |
| | 004F94BE | 005CE042 | (c) | |
| | 004F94BE | 005CE068 | (c) | |
| | 006115F2 | 00611666 | (c) | |