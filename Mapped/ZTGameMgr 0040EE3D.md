Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md) / [ZTGameMgr](ZTGameMgr.md)

# `ZTGameMgr::0x0040EE3D`

> [!notice]
> On further inspection, this function does not appear to be a function under ZTGameMgr. Will be moved.

This function is called inside of [ZTGameMgr::addToBudget](ZTGameMgr%20addToBudget%200040F018.md), but we know very little about how it operates yet. Below is a rough decompile from Ghidra to get a sense of what it might be doing. It looks like it's casting the budget value to an int32 and then making a comparison check for 0. 

Originally it was assumed that this was the check for the relief fund when zoo funds are low, but that turned out to be false. That job seems to belong to this function here: [[00635510 lowfunds_relief 005A13C5 \| 00635510::lowfunds_relief]]

# Table of Contents

[Decompile](#Decompile)
[XREFs](#XREFs)

# Decompile

Ghidra Decompile:

```C++
void FUN_0040ee3d(void)

{
  undefined uVar1;
  int local_18;
  undefined2 uVar3;
  undefined4 uVar2;
  
  local_18 = (int)(longlong)ROUND(*(float *)(GLOBAL_ZOO_BUDGET_STATUS + 0xc));
  uVar3 = (undefined2)((uint)(float *)(GLOBAL_ZOO_BUDGET_STATUS + 0xc) >> 0x10);
  if (local_18 < 1) {
    if (local_18 == 0) {
      uVar2 = CONCAT22(uVar3,DAT_00643184);
      uVar1 = DAT_00643186;
    }
    else {
      uVar2 = CONCAT22(uVar3,DAT_00643618);
      uVar1 = DAT_0064361a;
    }
  }
  else {
    uVar2 = CONCAT22(uVar3,DAT_00638fbc);
    uVar1 = DAT_00638fbe;
  }
  FUN_0040ee08((void *)((int)&UNK_00638ddb + 5),0x3f8,
               CONCAT13((char)((uint)uVar2 >> 0x18),CONCAT12(uVar1,(short)uVar2)));
  FUN_0040ed88(0x3f8,local_18,'\x01');
  return;
}
```

# XREFs

This function is accessed from the following locations and functions.

| Function Name | Function Location | Call Location | Access Type | Context |
| ---- | ---- | ---- | ---- | ---- |
| [ZTGameMgr::addToBudget](ZTGameMgr%20addToBudget%200040F018.md) | 0040F018 | 0040F02E | (c) | |
| | 00435055 | 0041D38D | (c) | |
| [ZTGameMgr::subtractFromBudget](ZTGameMgr%20subtractFromBudget%200041EF68.md) | 0041EF68 | 0041EF7E | (c) | |
| | 00519C1B | 00519C1C | (c) | |
