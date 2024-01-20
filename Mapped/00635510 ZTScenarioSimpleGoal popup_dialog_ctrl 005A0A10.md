Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md) / [00635510 ZTScenarioSimpleGoal](00635510%20ZTScenarioSimpleGoal.md)

# `00635510::popup_dialog_ctrl`

This function seems to control UI popups and among a few other controls. It is one of the ten functions controlled by [[00635510 ZTScenarioSimpleGoal trulea_switch 004FC783| 00635510::trulea_switch]]. 

# Analysis

It turns out that each one of these functions are the result of the `trulea` value described in the [Official Scenario Documentation Reference](app://obsidian.md/Official%20Scenario%20Documentation%20Reference). Below we can see the snippet relevant to this function:

```ini
; Trigger 2 (trulea = 2)
; targa (Varies)
; targb (Varies)
; Rules 1,3,5,7,9 have been made obsolete but still work.
; To fix them, replace the old rule by adding 1 - for example, 1 becomes 2.
;  0 Popup dialog.                  (targa layout ID,  targb unused)
;  2 Popup and click UI element.    (targa ele ID, targb layout if > 0)
;  4 Popup and disable UI element.  (targa ele ID, targb layout if > 0)
;  6 Popup and enable UI element.   (targa ele ID, targb layout if > 0)
;  8 Popup and hide UI element.     (targa ele ID, targb layout if > 0)
; 10 Popup and show UI element.     (targa ele ID, targb layout if > 0)
; 11 Popup any layout.              (targa layout ID,  targb pause flag)
; 12 Disable block of UI elements.  (targa block, targb layout if > 0)
; 13 Enable block of UI elements.   (targa block, targb layout if > 0)
; 14 Hide block of UI elements.     (targa block, targb layout if > 0)
; 15 Show block of UI elements.     (targa block, targb layout if > 0)
; 16 Set block of UI elements.      (targa block, targb layout if > 0)
; For 16, the entries in the block are <id>=enable,disable,hide,show
```

# Table of Contents

[[#Analysis]]
[[#Decompile]]
[[#XREFs]]

# Decompile

Below is a rough decompile from Ghidra:

```Cpp
void __thiscall OOAnalyzer::cls_0x635510::meth_0x5a0a10(cls_0x635510 *this,char param_1)

{
  char cVar1;
  undefined4 uVar2;
  char *pcVar3;
  uint uVar4;
  int *piVar5;
  void *this_00;
  byte bVar6;
  void *pvVar7;
  undefined4 *local_110;
  int local_10c;
  int local_108;
  char *local_104;
  byte local_100 [256];
  
  switch(this->mbr_0x34) {
  case 0:
    meth_0x4fc812(this,this->mbr_0x38,param_1);
    return;
  case 1:
  case 2:
    if (param_1 == '\0') {
      piVar5 = (int *)cls_0x40157d::meth_0x40157d
                                ((cls_0x40157d *)((int)&UNK_00638ddb + 5),this->mbr_0x38);
      if (piVar5 != (int *)0x0) {
        FUN_00506f04(piVar5);
      }
      meth_0x4fc812(this,this->mbr_0x3c,'\0');
      return;
    }
    break;
  case 3:
  case 4:
    uVar2 = FUN_005a0ddb(this->mbr_0x38);
    if ((char)uVar2 != '\0') {
      meth_0x4fc812(this,this->mbr_0x3c,param_1);
      return;
    }
    break;
  case 5:
  case 6:
    piVar5 = (int *)cls_0x40157d::meth_0x40157d
                              ((cls_0x40157d *)((int)&UNK_00638ddb + 5),this->mbr_0x38);
    if ((piVar5 != (int *)0x0) && (((uint)piVar5[0x1f] >> 0x13 & 1) != 0)) {
      (**(code **)(*piVar5 + 0x70))(0);
LAB_004579ec:
      meth_0x4fc812(this,this->mbr_0x3c,param_1);
      return;
    }
    break;
  case 7:
  case 8:
    uVar2 = FUN_0061c1bf((char *)this->mbr_0x38);
    if ((char)uVar2 != '\0') goto LAB_004579ec;
    break;
  case 9:
  case 10:
    piVar5 = (int *)cls_0x40157d::meth_0x40157d
                              ((cls_0x40157d *)((int)&UNK_00638ddb + 5),this->mbr_0x38);
    if ((piVar5 != (int *)0x0) && ((*(byte *)(piVar5 + 0x1f) & 1) != 0)) {
      (**(code **)(*piVar5 + 0x4c))();
      goto LAB_004579ec;
    }
    break;
  case 0xb:
    if (param_1 == '\0') {
      cls_0x40157d::meth_0x4fff2c
                ((cls_0x40157d *)((int)&UNK_00638ddb + 5),this->mbr_0x38,(undefined4 *)0x0,0,
                 (char *)0x0,0 < (int)this->mbr_0x3c,'\0',0,0);
      return;
    }
    break;
  case 0xc:
  case 0xd:
    FUN_0040ef4f(this->mbr_0x38,(char *)local_100,10);
    FUN_004aabb8((void *)this->mbr_0x4,&local_110);
    bVar6 = 0;
    uVar4 = 0;
    if (local_10c - (int)local_110 >> 2 != 0) {
      do {
        if (this->mbr_0x34 == 0xc) {
          uVar2 = FUN_005a0ddb(local_110[uVar4]);
          bVar6 = bVar6 | (byte)uVar2;
        }
        else {
          piVar5 = (int *)cls_0x40157d::meth_0x40157d
                                    ((cls_0x40157d *)((int)&UNK_00638ddb + 5),local_110[uVar4]);
          if ((piVar5 != (int *)0x0) && (((uint)piVar5[0x1f] >> 0x13 & 1) != 0)) {
            (**(code **)(*piVar5 + 0x70))(0);
            bVar6 = 1;
          }
        }
        uVar4 = uVar4 + 1;
      } while (uVar4 < (uint)(local_10c - (int)local_110 >> 2));
      if (bVar6 != 0) {
        meth_0x4fc812(this,this->mbr_0x3c,param_1);
      }
    }
    if (local_110 != (undefined4 *)0x0) {
      FUN_00401b16(local_110,(local_108 - (int)local_110 >> 2) << 2);
      return;
    }
    break;
  case 0xe:
  case 0xf:
    FUN_0040ef4f(this->mbr_0x38,(char *)local_100,10);
    FUN_004aabb8((void *)this->mbr_0x4,&local_110);
    bVar6 = 0;
    uVar4 = 0;
    if (local_10c - (int)local_110 >> 2 != 0) {
      do {
        if (this->mbr_0x34 == 0xe) {
          uVar2 = FUN_0061c1bf((char *)local_110[uVar4]);
          bVar6 = bVar6 | (byte)uVar2;
        }
        else {
          piVar5 = (int *)cls_0x40157d::meth_0x40157d
                                    ((cls_0x40157d *)((int)&UNK_00638ddb + 5),local_110[uVar4]);
          if ((piVar5 != (int *)0x0) && ((*(byte *)(piVar5 + 0x1f) & 1) != 0)) {
            (**(code **)(*piVar5 + 0x4c))();
            bVar6 = 1;
          }
        }
        uVar4 = uVar4 + 1;
      } while (uVar4 < (uint)(local_10c - (int)local_110 >> 2));
      if (bVar6 != 0) {
        meth_0x4fc812(this,this->mbr_0x3c,param_1);
      }
    }
    if (local_110 != (undefined4 *)0x0) {
      uVar4 = (local_108 - (int)local_110 >> 2) * 4;
      if (0x80 < uVar4) {
        FUN_00402629(local_110);
        return;
      }
      uVar4 = uVar4 - 1 >> 3;
      *local_110 = (&DAT_00638000)[uVar4];
      (&DAT_00638000)[uVar4] = local_110;
      return;
    }
    break;
  case 0x10:
    FUN_0040ef4f(this->mbr_0x38,(char *)local_100,10);
    OOAnalyzer::cls_0x404fd6::meth_0x409cf3((cls_0x404fd6 *)this->mbr_0x4,&local_110,local_100);
    pvVar7 = (void *)0x0;
    this_00 = (void *)(local_10c - (int)local_110 >> 2);
    if (this_00 != (void *)0x0) {
      do {
        local_104 = (char *)0x0;
        pcVar3 = (char *)FUN_00405218(this_00,(byte *)local_110[(int)pvVar7]);
        uVar4 = OOAnalyzer::cls_0x404fd6::meth_0x4098c1
                          ((cls_0x404fd6 *)this->mbr_0x4,local_100,local_110[(int)pvVar7],&local_104
                          );
        if ((((char)uVar4 != '\0') && (local_104 != (char *)0x0)) &&
           (cVar1 = *local_104, cVar1 != '\0')) {
          if (cVar1 == 'd') {
            FUN_005a0ddb((int)pcVar3);
          }
          else if (cVar1 == 'e') {
            piVar5 = (int *)cls_0x40157d::meth_0x40157d
                                      ((cls_0x40157d *)((int)&UNK_00638ddb + 5),(int)pcVar3);
            if (piVar5 != (int *)0x0) {
              (**(code **)(*piVar5 + 0x70))(0);
            }
          }
          else if (cVar1 == 'h') {
            FUN_0061c1bf(pcVar3);
          }
          else if ((cVar1 == 's') &&
                  (piVar5 = (int *)cls_0x40157d::meth_0x40157d
                                             ((cls_0x40157d *)((int)&UNK_00638ddb + 5),(int)pcVar3),
                  piVar5 != (int *)0x0)) {
            (**(code **)(*piVar5 + 0x4c))();
          }
        }
        pvVar7 = (void *)((int)pvVar7 + 1);
        this_00 = (void *)(local_10c - (int)local_110 >> 2);
      } while (pvVar7 < this_00);
    }
    meth_0x4fc812(this,this->mbr_0x3c,param_1);
    if (local_110 != (undefined4 *)0x0) {
      uVar4 = (local_108 - (int)local_110 >> 2) * 4;
      if (0x80 < uVar4) {
        FUN_00402629(local_110);
        return;
      }
      uVar4 = uVar4 - 1 >> 3;
      *local_110 = (&DAT_00638000)[uVar4];
      (&DAT_00638000)[uVar4] = local_110;
    }
  }
  return;
}
```

# XREFs

| Function Name | Function Location | Call Location | Access Type | Context |
| ---- | ---- | ---- | ---- | ---- |
| [[00635510 ZTScenarioSimpleGoal trulea_switch 004FC783| 00635510::trulea_switch]] | 004FC783 | 004FC7A8 | (c) | Controls ten functions given the value of the `trulea` value found in SCN files. |

