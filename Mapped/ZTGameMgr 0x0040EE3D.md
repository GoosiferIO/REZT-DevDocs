# `ZTGameMgr::0x0040EE3D`

This function is called inside of [ZTGameMgr::addToBudget](ZTGameMgr%20addToBudget.md), but we know very little about how it operates yet. Below is a rough decompile from Ghidra to get a sense of what it might be doing. It looks like it's casting the budget value to an int32, then making a comparison check to 0. 

Originally it was assumed that this was the check for the relief fund when zoo funds are low, but that turned out to be false. That function lives here: 

**Ghidra Decompile:**

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