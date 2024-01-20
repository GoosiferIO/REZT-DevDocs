Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md) / [00635510 ZTScenarioSimpleGoal](00635510%20ZTScenarioSimpleGoal.md)

# `00635510::005A13C5`

This function decides whether to give a player 500,000 or 10,000 from the relief fund, among other things most of which are yet to be figured out. It is one of the ten functions controlled by [[00635510 ZTScenarioSimpleGoal trulea_switch 004FC783| 00635510::trulea_switch]]. 

# Table of Contents

[Decompile](#Decompile)
[XREFs](#XREFs)

# Analysis

It turns out that each one of these functions are the result of the `trulea` value described in the [[Official Scenario Documentation Reference]]. Below we can see the snippet relevant to this function:

```ini
; Trigger 3 (trulea = 3)
; targa (Amount of cash.)
; targb (Unused or resource ID for message - use %s to capture dollar amount.)
; 0 Donate cash. (Shows up in donations column.)
; 1 Add cash. (Doesn't show up in finance sheet.)
; 2 Set cash. (Brute force sets the cash amount.)
```

# Decompile 

A rough decompile from Ghidra:

```Cpp
void __thiscall FUN_005a13c5(void *this,char param_1)

{
  int iVar1;
  int iVar2;
  float fVar3;
  cls_0x40f018 *this_00;
  undefined4 *puVar4;
  uint uVar5;
  float10 fVar6;
  undefined4 **ppuVar7;
  float fVar8;
  undefined4 *puVar9;
  undefined4 *local_18 [2];
  int local_10;
  undefined4 *local_c [2];
  int local_4;
  
  this_00 = GLOBAL_ZOO_BUDGET_STATUS;
  if (param_1 != '\0') {
    return;
  }
  iVar1 = *(int *)((int)this + 0x38);
  fVar3 = (float)iVar1;
  iVar2 = *(int *)((int)this + 0x34);
  fVar8 = fVar3;
  if (iVar2 == 0) {
    OOAnalyzer::cls_0x42ebbe::meth_0x42ebbe
              ((cls_0x42ebbe *)&GLOBAL_ZOO_BUDGET_STATUS->mbr_0x10,fVar3);
  }
  else if (iVar2 != 1) {
    if (iVar2 != 2) goto LAB_005a167e;
    fVar6 = FUN_00404fcc((float *)&GLOBAL_ZOO_BUDGET_STATUS->field_0xc);
    fVar8 = (float)((float10)iVar1 - fVar6);
  }
  OOAnalyzer::cls_0x40f018::meth_0x40f018(this_00,fVar8);
LAB_005a167e:
  if (0 < *(int *)((int)this + 0x3c)) {
    FUN_004ef4d4(local_c,fVar3,'\x01');
    puVar9 = *(undefined4 **)((int)this + 0x3c);
    ppuVar7 = local_18;
    puVar4 = FUN_004010c7();
    FUN_0041ca7f(puVar4,ppuVar7,puVar9);
    OOAnalyzer::cls_0x40157d::meth_0x49cec0
              ((cls_0x40157d *)((int)&UNK_00638ddb + 5),(int *)local_18,4,0,0,'\x01',0);
    if (local_18[0] != (undefined4 *)0x0) {
      if ((uint)(local_10 - (int)local_18[0]) < 0x81) {
        uVar5 = (local_10 - (int)local_18[0]) - 1U >> 3;
        *local_18[0] = (&DAT_00638000)[uVar5];
        (&DAT_00638000)[uVar5] = local_18[0];
      }
      else {
        FUN_00402629(local_18[0]);
      }
    }
    if (local_c[0] != (undefined4 *)0x0) {
      if (0x80 < (uint)(local_4 - (int)local_c[0])) {
        FUN_00402629(local_c[0]);
        return;
      }
      uVar5 = (local_4 - (int)local_c[0]) - 1U >> 3;
      *local_c[0] = (&DAT_00638000)[uVar5];
      (&DAT_00638000)[uVar5] = local_c[0];
    }
  }
  return;
}
```

# XREFs

This function seems to be referenced from the following locations:

| Function Name | Function Location | Call Location | Access Type | Context |
| ---- | ---- | ---- | ---- | ---- |
| [[00635510 ZTScenarioSimpleGoal trulea_switch 004FC783| 00635510::trulea_switch]] | 004FC783 | 005A13E5 | (c) | Appears to be part of some switch statement and is a function call given a true conditional. It is among 10 other functions in this switch statement. |