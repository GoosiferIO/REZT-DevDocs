Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md) / [Global Functions](../General/Global%20Functions.md)

# ztSecrets

This function is located at `0044940B`. It does not appear to be part of a greater class.

This function serves as a switchboard for all of the cheat, easter egg, and secret functions in the game. For the purpose of sanity, we will call all three 'secrets.' To read a full list of all of the secrets in this game, please see: [ZT1 All Cheats and Easter Eggs](../General/ZT1%20All%20Cheats%20and%20Easter%20Eggs.md)

Every staff or guest name is explicitly named and a conditional in the switch statement, so it's possible that they're not actually pulled from a serialized data container or a configuration file--these might be strings that are hardcoded into the switch statement. However, this function has not yet been tested, and the only reason this is brought up is because other decompilation tools present the names as strings, while Ghidra shows a data container with a named label.

Note that the only cheat whose 'cheat name' *is not* explicitly named inside of this structure is the [Jonathan Gilmour Cheat](ZTGameMgr%20jonathanGilmourTribute%20006089E8.md). 

`ztSecrets` has not been completely studied, but will help reverse many other areas of the code.

# Table of Contents

[[#Decompile]]
[[#XREFs]]

# Decompile

```C++
void __cdecl FUN_0044940b(int *param_1,undefined4 param_2,byte **param_3)

{
  undefined *puVar1;
  int iVar2;
  ZTResearchMgr *this;
  byte **ppbVar3;
  char cVar4;
  int *piVar5;
  int iVar6;
  byte **ppbVar7;
  cls_0x619215 *this_00;
  cls_0x61922d *this_01;
  undefined4 uVar8;
  cls_0x404fd6 *this_02;
  uint uVar9;
  byte *pbVar10;
  cls_0x6354e4::vftable_6354e4 *pcVar11;
  char *pcVar12;
  char **ppcVar13;
  char *pcVar14;
  byte *pbVar15;
  bool bVar16;
  byte **ppbVar17;
  int iStack_1c;
  cls_0x6354e4::vftable_6354e4 *pcStack_18;
  dword dStack_14;
  dword dStack_10;
  cls_0x6354e4::vftable_6354e4 *pcStack_c;
  dword dStack_8;
  dword dStack_4;
  
  ppbVar3 = param_3;
  if (param_1 == (int *)0x0) {
LAB_0044947e:
    if ((param_1 == (int *)0x0) ||
       (cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638690), piVar5 = param_1,
       cVar4 == '\0')) {
      piVar5 = (int *)0x0;
    }
    if (piVar5 != (int *)0x0) {
      iVar6 = (**(code **)(*(int *)param_1[0x4a] + 0x20))();
      if (iVar6 == 0x1398) {
        ppbVar17 = ppbVar3;
        ppcVar13 = (char **)OOAnalyzer::cls_0x6354e4::meth_0x40505a
                                      ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)&DAT_00651ef4);
        uVar8 = FUN_0040da1d(ppcVar13,(char **)ppbVar17);
        OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
        if ((char)uVar8 != '\0') {
          DAT_00654ad9 = 1;
          FUN_006075ea();
          goto LAB_004494b5;
        }
      }
      iVar6 = (**(code **)(*(int *)param_1[0x4a] + 0x20))();
      if (iVar6 == 0x14b4) {
        ppbVar17 = ppbVar3;
        ppcVar13 = (char **)OOAnalyzer::cls_0x6354e4::meth_0x40505a
                                      ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)s_Comet_00651eec);
        uVar8 = FUN_0040da1d(ppcVar13,(char **)ppbVar17);
        OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
        if ((char)uVar8 != '\0') {
          FUN_00607757();
        }
      }
    }
    goto LAB_004494b5;
  }
  cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638700);
  if (cVar4 == '\0') {
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638770);
    if (cVar4 != '\0') {
      OOAnalyzer::cls_0x6354e4::meth_0x401070((cls_0x6354e4 *)&pcStack_c);
      uVar9 = 0xffffffff;
      pcVar12 = s_Rosalie_00651efc;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)s_Rosalie_00651efc,~uVar9 + 0x651efb);
      iVar6 = dStack_8 - (int)pcStack_c;
      if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
        bVar16 = true;
        pcVar11 = pcStack_c;
        pbVar10 = *ppbVar3;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          pbVar10 = pbVar10 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_005cb2be;
        OOAnalyzer::cls_0x6354e4::meth_0x401070((cls_0x6354e4 *)&pcStack_18);
        uVar9 = 0xffffffff;
        pcVar12 = &DAT_00639014;
        do {
          if (uVar9 == 0) break;
          uVar9 = uVar9 - 1;
          cVar4 = *pcVar12;
          pcVar12 = pcVar12 + 1;
        } while (cVar4 != '\0');
        OOAnalyzer::cls_0x6354e4::meth_0x401a94
                  ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)&DAT_00639014,~uVar9 + 0x639013);
        pcVar12 = *(char **)(param_1[0x4a] + 0xa4);
        iVar6 = *(int *)(param_1[0x4a] + 0xa8) - (int)pcVar12;
        if (iVar6 == dStack_14 - (int)pcStack_18) {
          bVar16 = true;
          pcVar11 = pcStack_18;
          do {
            if (iVar6 == 0) break;
            iVar6 = iVar6 + -1;
            bVar16 = *pcVar12 == *(char *)&pcVar11->~cls_0x6354e4_0;
            pcVar12 = pcVar12 + 1;
            pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          } while (bVar16);
          if (!bVar16) goto LAB_005cb2ab;
          bVar16 = true;
        }
        else {
LAB_005cb2ab:
          bVar16 = false;
        }
        OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
        if (!bVar16) goto LAB_005cb2be;
        bVar16 = true;
      }
      else {
LAB_005cb2be:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
      if (bVar16) {
        DAT_00654ad8 = 1;
      }
      goto LAB_004494b5;
    }
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638780);
    if (cVar4 != '\0') {
      pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
      dStack_14 = 0;
      dStack_10 = 0;
      uVar9 = 0xffffffff;
      pcVar12 = s_George_W_0064e88c;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_George_W_0064e88c,~uVar9 + 0x64e88b);
      iVar6 = dStack_14 - (int)pcStack_18;
      if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
        bVar16 = true;
        pcVar11 = pcStack_18;
        pbVar10 = *ppbVar3;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          pbVar10 = pbVar10 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_00483e15;
        OOAnalyzer::cls_0x6354e4::meth_0x401070((cls_0x6354e4 *)&pcStack_c);
        uVar9 = 0xffffffff;
        pcVar12 = &DAT_00639020;
        do {
          if (uVar9 == 0) break;
          uVar9 = uVar9 - 1;
          cVar4 = *pcVar12;
          pcVar12 = pcVar12 + 1;
        } while (cVar4 != '\0');
        OOAnalyzer::cls_0x6354e4::meth_0x401a94
                  ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)&DAT_00639020,~uVar9 + 0x63901f);
        pcVar12 = *(char **)(param_1[0x4a] + 0xa4);
        iVar6 = *(int *)(param_1[0x4a] + 0xa8) - (int)pcVar12;
        if (iVar6 == dStack_8 - (int)pcStack_c) {
          bVar16 = true;
          pcVar11 = pcStack_c;
          do {
            if (iVar6 == 0) break;
            iVar6 = iVar6 + -1;
            bVar16 = *pcVar12 == *(char *)&pcVar11->~cls_0x6354e4_0;
            pcVar12 = pcVar12 + 1;
            pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          } while (bVar16);
          if (!bVar16) goto LAB_005cb345;
          bVar16 = true;
        }
        else {
LAB_005cb345:
          bVar16 = false;
        }
        OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
        if (!bVar16) goto LAB_00483e15;
        bVar16 = true;
      }
      else {
LAB_00483e15:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
      if (bVar16) {
        FUN_00607174();
        goto LAB_004494b5;
      }
      pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
      dStack_14 = 0;
      dStack_10 = 0;
      uVar9 = 0xffffffff;
      pcVar12 = s_Bob_V_0064e884;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Bob_V_0064e884,~uVar9 + 0x64e883);
      iVar6 = dStack_14 - (int)pcStack_18;
      if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
        bVar16 = true;
        pcVar11 = pcStack_18;
        pbVar10 = *ppbVar3;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          pbVar10 = pbVar10 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_00483e7e;
        OOAnalyzer::cls_0x6354e4::meth_0x401070((cls_0x6354e4 *)&pcStack_c);
        uVar9 = 0xffffffff;
        pcVar12 = &DAT_00639020;
        do {
          if (uVar9 == 0) break;
          uVar9 = uVar9 - 1;
          cVar4 = *pcVar12;
          pcVar12 = pcVar12 + 1;
        } while (cVar4 != '\0');
        OOAnalyzer::cls_0x6354e4::meth_0x401a94
                  ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)&DAT_00639020,~uVar9 + 0x63901f);
        pcVar12 = *(char **)(param_1[0x4a] + 0xa4);
        iVar6 = *(int *)(param_1[0x4a] + 0xa8) - (int)pcVar12;
        if (iVar6 == dStack_8 - (int)pcStack_c) {
          bVar16 = true;
          pcVar11 = pcStack_c;
          do {
            if (iVar6 == 0) break;
            iVar6 = iVar6 + -1;
            bVar16 = *pcVar12 == *(char *)&pcVar11->~cls_0x6354e4_0;
            pcVar12 = pcVar12 + 1;
            pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          } while (bVar16);
          if (!bVar16) goto LAB_005cb3d5;
          bVar16 = true;
        }
        else {
LAB_005cb3d5:
          bVar16 = false;
        }
        OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
        if (!bVar16) goto LAB_00483e7e;
        bVar16 = true;
      }
      else {
LAB_00483e7e:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
      if (bVar16) {
        FUN_006070ef();
        goto LAB_004494b5;
      }
      pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
      dStack_14 = 0;
      dStack_10 = 0;
      uVar9 = 0xffffffff;
      pcVar12 = s_The_Rock_0064e878;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_The_Rock_0064e878,~uVar9 + 0x64e877);
      iVar6 = dStack_14 - (int)pcStack_18;
      if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
        bVar16 = true;
        pcVar11 = pcStack_18;
        pbVar10 = *ppbVar3;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          pbVar10 = pbVar10 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_00483ee7;
        OOAnalyzer::cls_0x6354e4::meth_0x401070((cls_0x6354e4 *)&pcStack_c);
        uVar9 = 0xffffffff;
        pcVar12 = &DAT_00639020;
        do {
          if (uVar9 == 0) break;
          uVar9 = uVar9 - 1;
          cVar4 = *pcVar12;
          pcVar12 = pcVar12 + 1;
        } while (cVar4 != '\0');
        OOAnalyzer::cls_0x6354e4::meth_0x401a94
                  ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)&DAT_00639020,~uVar9 + 0x63901f);
        pcVar12 = *(char **)(param_1[0x4a] + 0xa4);
        iVar6 = *(int *)(param_1[0x4a] + 0xa8) - (int)pcVar12;
        if (iVar6 == dStack_8 - (int)pcStack_c) {
          bVar16 = true;
          pcVar11 = pcStack_c;
          do {
            if (iVar6 == 0) break;
            iVar6 = iVar6 + -1;
            bVar16 = *pcVar12 == *(char *)&pcVar11->~cls_0x6354e4_0;
            pcVar12 = pcVar12 + 1;
            pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          } while (bVar16);
          if (!bVar16) goto LAB_005cb465;
          bVar16 = true;
        }
        else {
LAB_005cb465:
          bVar16 = false;
        }
        OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
        if (!bVar16) goto LAB_00483ee7;
        bVar16 = true;
      }
      else {
LAB_00483ee7:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
      if (bVar16) {
        FUN_0060d694();
      }
      goto LAB_004494b5;
    }
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638760);
    if (cVar4 == '\0') goto LAB_0044947e;
    pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
    dStack_14 = 0;
    dStack_10 = 0;
    uVar9 = 0xffffffff;
    pcVar12 = s_Dr._Dolittle_0064e7cc;
    do {
      if (uVar9 == 0) break;
      uVar9 = uVar9 - 1;
      cVar4 = *pcVar12;
      pcVar12 = pcVar12 + 1;
    } while (cVar4 != '\0');
    OOAnalyzer::cls_0x6354e4::meth_0x401a94
              ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Dr._Dolittle_0064e7cc,
               (int)(&UNK_0064e7cb + ~uVar9));
    iVar6 = dStack_14 - (int)pcStack_18;
    if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
      bVar16 = true;
      pcVar11 = pcStack_18;
      pbVar10 = *ppbVar3;
      do {
        if (iVar6 == 0) break;
        iVar6 = iVar6 + -1;
        bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
        pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
        pbVar10 = pbVar10 + 1;
      } while (bVar16);
      if (!bVar16) goto LAB_004e7810;
      OOAnalyzer::cls_0x6354e4::meth_0x401070((cls_0x6354e4 *)&pcStack_c);
      uVar9 = 0xffffffff;
      pcVar12 = &DAT_00639020;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)&DAT_00639020,~uVar9 + 0x63901f);
      pcVar12 = *(char **)(param_1[0x4a] + 0xa4);
      iVar6 = *(int *)(param_1[0x4a] + 0xa8) - (int)pcVar12;
      if (iVar6 == dStack_8 - (int)pcStack_c) {
        bVar16 = true;
        pcVar11 = pcStack_c;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *pcVar12 == *(char *)&pcVar11->~cls_0x6354e4_0;
          pcVar12 = pcVar12 + 1;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
        } while (bVar16);
        if (!bVar16) goto LAB_005cb4ed;
        bVar16 = true;
      }
      else {
LAB_005cb4ed:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
      if (!bVar16) goto LAB_004e7810;
      bVar16 = true;
    }
    else {
LAB_004e7810:
      bVar16 = false;
    }
    OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
    if (bVar16) {
      DAT_0063c2e3 = 1;
      goto LAB_004494b5;
    }
    iVar6 = (**(code **)(*(int *)param_1[0x4a] + 0x20))();
    if (iVar6 == 0x254f) {
      pcStack_c = (cls_0x6354e4::vftable_6354e4 *)0x0;
      dStack_8 = 0;
      dStack_4 = 0;
      uVar9 = 0xffffffff;
      pcVar12 = s_Dr._Scholl_006460c0;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)s_Dr._Scholl_006460c0,~uVar9 + 0x6460bf);
      iVar6 = dStack_8 - (int)pcStack_c;
      if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
        bVar16 = true;
        pcVar11 = pcStack_c;
        pbVar10 = *ppbVar3;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          pbVar10 = pbVar10 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_00482ef4;
        bVar16 = true;
      }
      else {
LAB_00482ef4:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
      if (bVar16) {
        cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_006386b0);
        if (cVar4 != '\0') {
          DAT_0063c2e4 = 1;
          (**(code **)(*param_1 + 0x1c0))(param_1[0x7e] << 1);
        }
        goto LAB_004494b5;
      }
    }
    pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
    dStack_14 = 0;
    dStack_10 = 0;
    uVar9 = 0xffffffff;
    pcVar12 = &DAT_00639014;
    do {
      if (uVar9 == 0) break;
      uVar9 = uVar9 - 1;
      cVar4 = *pcVar12;
      pcVar12 = pcVar12 + 1;
    } while (cVar4 != '\0');
    OOAnalyzer::cls_0x6354e4::meth_0x401a94
              ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)&DAT_00639014,~uVar9 + 0x639013);
    pcVar12 = *(char **)(param_1[0x4a] + 0xa4);
    iVar6 = *(int *)(param_1[0x4a] + 0xa8) - (int)pcVar12;
    if (iVar6 == dStack_14 - (int)pcStack_18) {
      bVar16 = true;
      pcVar11 = pcStack_18;
      do {
        if (iVar6 == 0) break;
        iVar6 = iVar6 + -1;
        bVar16 = *pcVar12 == *(char *)&pcVar11->~cls_0x6354e4_0;
        pcVar12 = pcVar12 + 1;
        pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      } while (bVar16);
      if (!bVar16) goto LAB_004e78a9;
      pcStack_c = (cls_0x6354e4::vftable_6354e4 *)0x0;
      dStack_8 = 0;
      dStack_4 = 0;
      uVar9 = 0xffffffff;
      pcVar12 = s_Susan_Kittleson_0064e7ec;
      do {
        if (uVar9 == 0) break;
        uVar9 = uVar9 - 1;
        cVar4 = *pcVar12;
        pcVar12 = pcVar12 + 1;
      } while (cVar4 != '\0');
      OOAnalyzer::cls_0x6354e4::meth_0x401a94
                ((cls_0x6354e4 *)&pcStack_c,(undefined4 *)s_Susan_Kittleson_0064e7ec,
                 (int)(&UNK_0064e7eb + ~uVar9));
      iVar6 = dStack_8 - (int)pcStack_c;
      if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
        bVar16 = true;
        pcVar11 = pcStack_c;
        pbVar10 = *ppbVar3;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
          pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
          pbVar10 = pbVar10 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_004e7a65;
        bVar16 = true;
      }
      else {
LAB_004e7a65:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
      if (!bVar16) goto LAB_004e78a9;
      bVar16 = true;
    }
    else {
LAB_004e78a9:
      bVar16 = false;
    }
    OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
    if (bVar16) {
      DAT_006392c1 = 1;
      goto LAB_004494b5;
    }
    iVar6 = param_1[0x4a];
    ppcVar13 = (char **)OOAnalyzer::cls_0x6354e4::meth_0x40505a
                                  ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)&DAT_00639020);
    pcVar12 = *(char **)(iVar6 + 0xa4);
    iVar6 = *(int *)(iVar6 + 0xa8) - (int)pcVar12;
    if (iVar6 == (int)ppcVar13[1] - (int)*ppcVar13) {
      bVar16 = true;
      pcVar14 = *ppcVar13;
      do {
        if (iVar6 == 0) break;
        iVar6 = iVar6 + -1;
        bVar16 = *pcVar12 == *pcVar14;
        pcVar12 = pcVar12 + 1;
        pcVar14 = pcVar14 + 1;
      } while (bVar16);
      if (!bVar16) goto LAB_004e7900;
      bVar16 = true;
    }
    else {
LAB_004e7900:
      bVar16 = false;
    }
    if (bVar16) {
      ppbVar17 = ppbVar3;
      ppbVar7 = (byte **)OOAnalyzer::cls_0x6354e4::meth_0x40505a
                                   ((cls_0x6354e4 *)&pcStack_c,
                                    (undefined4 *)s_Chuck_Frizelle_0064e7dc);
      iVar6 = (int)ppbVar7[1] - (int)*ppbVar7;
      if (iVar6 == (int)ppbVar17[1] - (int)*ppbVar17) {
        bVar16 = true;
        pbVar10 = *ppbVar7;
        pbVar15 = *ppbVar17;
        do {
          if (iVar6 == 0) break;
          iVar6 = iVar6 + -1;
          bVar16 = *pbVar10 == *pbVar15;
          pbVar10 = pbVar10 + 1;
          pbVar15 = pbVar15 + 1;
        } while (bVar16);
        if (!bVar16) goto LAB_004e7951;
        bVar16 = true;
      }
      else {
LAB_004e7951:
        bVar16 = false;
      }
      OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
      if (!bVar16) goto LAB_004e797d;
      bVar16 = true;
    }
    else {
LAB_004e797d:
      bVar16 = false;
    }
    OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
    if (bVar16) {
      DAT_006392c1 = 1;
      goto LAB_004494b5;
    }
    iVar6 = (**(code **)(*(int *)param_1[0x4a] + 0x20))();
    if (iVar6 != 0x254f) goto LAB_004494b5;
    ppbVar17 = ppbVar3;
    ppbVar7 = (byte **)OOAnalyzer::cls_0x6354e4::meth_0x40505a
                                 ((cls_0x6354e4 *)&pcStack_c,
                                  (undefined4 *)s_Dr._Frankenstein_006460ac);
    iVar6 = (int)ppbVar7[1] - (int)*ppbVar7;
    if (iVar6 == (int)ppbVar17[1] - (int)*ppbVar17) {
      bVar16 = true;
      pbVar10 = *ppbVar7;
      pbVar15 = *ppbVar17;
      do {
        if (iVar6 == 0) break;
        iVar6 = iVar6 + -1;
        bVar16 = *pbVar10 == *pbVar15;
        pbVar10 = pbVar10 + 1;
        pbVar15 = pbVar15 + 1;
      } while (bVar16);
      if (!bVar16) goto LAB_004e79de;
      bVar16 = true;
    }
    else {
LAB_004e79de:
      bVar16 = false;
    }
    OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_c);
    if (bVar16) {
      DAT_0064e83a = 1;
    }
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Alfred_H_0063cabc;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Alfred_H_0063cabc,~uVar9 + 0x63cabb);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f734b;
    bVar16 = true;
  }
  else {
LAB_004f734b:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607552();
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Russell_C_0063cab0;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Russell_C_0063cab0,~uVar9 + 0x63caaf);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f73b4;
    bVar16 = true;
  }
  else {
LAB_004f73b4:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_006074ed();
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Mr._Pink_0063caa4;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Mr._Pink_0063caa4,
             (int)(&UNK_0063caa3 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f741d;
    bVar16 = true;
  }
  else {
LAB_004f741d:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060739a(8,0,0);
    FUN_006072e4(0x15,0x10);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Mr._Orange_0063ca98;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Mr._Orange_0063ca98,~uVar9 + 0x63ca97);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7486;
    bVar16 = true;
  }
  else {
LAB_004f7486:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060739a(10,1,0);
    FUN_006072e4(7,0xb);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Mr._Brown_0063ca8c;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Mr._Brown_0063ca8c,~uVar9 + 0x63ca8b);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f74ef;
    bVar16 = true;
  }
  else {
LAB_004f74ef:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060739a(0xe,5,0);
    FUN_006072e4(0xe,0x13);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Mr._White_0063ca80;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Mr._White_0063ca80,~uVar9 + 0x63ca7f);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7558;
    bVar16 = true;
  }
  else {
LAB_004f7558:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060739a(0,6,1);
    FUN_006072e4(0x17,4);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Mr._Blue_0063ca74;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Mr._Blue_0063ca74,
             (int)(&UNK_0063ca73 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f75c1;
    bVar16 = true;
  }
  else {
LAB_004f75c1:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060739a(0xf,0,3);
    FUN_006072e4(0,0x16);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Mr._Blonde_0063ca68;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Mr._Blonde_0063ca68,
             (int)(&UNK_0063ca67 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f762a;
    bVar16 = true;
  }
  else {
LAB_004f762a:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060739a(9,1,4);
    FUN_006072e4(0xf,0xc);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Steve_Serafino_0063ca58;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Steve_Serafino_0063ca58,~uVar9 + 0x63ca57);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7693;
    bVar16 = true;
  }
  else {
LAB_004f7693:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa1);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Charlie_Peterson_0063ca44;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Charlie_Peterson_0063ca44,~uVar9 + 0x63ca43
            );
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f76fc;
    bVar16 = true;
  }
  else {
LAB_004f76fc:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa2);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_John_Wheeler_0063ca34;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_John_Wheeler_0063ca34,~uVar9 + 0x63ca33);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7765;
    bVar16 = true;
  }
  else {
LAB_004f7765:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa3);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Andrew_Binder_0063ca24;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Andrew_Binder_0063ca24,
             (int)(&UNK_0063ca23 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f77ce;
    bVar16 = true;
  }
  else {
LAB_004f77ce:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa4);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Hank_Howie_0063ca18;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Hank_Howie_0063ca18,~uVar9 + 0x63ca17);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7837;
    bVar16 = true;
  }
  else {
LAB_004f7837:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa5);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Adam_Levesque_0063ca08;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Adam_Levesque_0063ca08,~uVar9 + 0x63ca07);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f78a0;
    bVar16 = true;
  }
  else {
LAB_004f78a0:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa6);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Lou_Catanzaro_0063c9f8;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Lou_Catanzaro_0063c9f8,~uVar9 + 0x63c9f7);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7909;
    bVar16 = true;
  }
  else {
LAB_004f7909:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aa7);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Zeta_Psi_0063cb2c;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Zeta_Psi_0063cb2c,
             (int)(s_Akiyama_0063cb24 + ~uVar9 + 7));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7972;
    bVar16 = true;
  }
  else {
LAB_004f7972:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607434();
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Akiyama_0063cb24;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Akiyama_0063cb24,
             (int)(&UNK_0063cb23 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f79db;
    bVar16 = true;
  }
  else {
LAB_004f79db:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_006000d3(DAT_00638ff8);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Eggman_0063cb1c;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Eggman_0063cb1c,
             (int)(s_Dinoman_0063cb14 + ~uVar9 + 7));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7a44;
    bVar16 = true;
  }
  else {
LAB_004f7a44:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    DAT_0063cfa1 = 1;
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Dinoman_0063cb14;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Dinoman_0063cb14,
             (int)(&UNK_0063cb13 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7aad;
    bVar16 = true;
  }
  else {
LAB_004f7aad:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aad);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Ron_Propst_0063cb08;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Ron_Propst_0063cb08,~uVar9 + 0x63cb07);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7b16;
    bVar16 = true;
  }
  else {
LAB_004f7b16:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_00607001(0x5aae);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Marwan_Jubran_0063caf8;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Marwan_Jubran_0063caf8,
             (int)(&UNK_0063caf7 + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7b7f;
    bVar16 = true;
  }
  else {
LAB_004f7b7f:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    FUN_0060d8e3(DAT_00638040);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Stinky_0063caf0;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Stinky_0063caf0,~uVar9 + 0x63caef);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if (!bVar16) goto LAB_004f7be8;
    bVar16 = true;
  }
  else {
LAB_004f7be8:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638700);
    pbVar10 = (byte *)((-(uint)(cVar4 != '\0') & (uint)param_1) + 0x340);
    *pbVar10 = *pbVar10 | 2;
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = &DAT_0063cae8;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)&DAT_0063cae8,~uVar9 + 0x63cae7);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if ((!bVar16) || (**(char **)(param_1[0x4a] + 0x98) != 'm')) goto LAB_004f7c51;
    bVar16 = true;
  }
  else {
LAB_004f7c51:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638700);
    pbVar10 = (byte *)((-(uint)(cVar4 != '\0') & (uint)param_1) + 0x340);
    *pbVar10 = *pbVar10 | 4;
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Boogyman_0063cadc;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Boogyman_0063cadc,~uVar9 + 0x63cadb);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if ((!bVar16) || (**(char **)(param_1[0x4a] + 0x98) != 'm')) goto LAB_004f7cba;
    bVar16 = true;
  }
  else {
LAB_004f7cba:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638700);
    pbVar10 = (byte *)((-(uint)(cVar4 != '\0') & (uint)param_1) + 0x340);
    *pbVar10 = *pbVar10 | 8;
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Yellowman_0063cad0;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Yellowman_0063cad0,
             (int)(&UNK_0063cacf + ~uVar9));
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if ((!bVar16) || (**(char **)(param_1[0x4a] + 0x98) != 'm')) goto LAB_004f7d23;
    bVar16 = true;
  }
  else {
LAB_004f7d23:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638700);
    this_00 = (cls_0x619215 *)(-(uint)(cVar4 != '\0') & (uint)param_1);
    puVar1 = &this_00[3].field_0x34;
    *puVar1 = *puVar1 | 0x10;
    OOAnalyzer::cls_0x619215::meth_0x619215(this_00);
    goto LAB_004494b5;
  }
  pcStack_18 = (cls_0x6354e4::vftable_6354e4 *)0x0;
  dStack_14 = 0;
  dStack_10 = 0;
  uVar9 = 0xffffffff;
  pcVar12 = s_Redman_0063cac8;
  do {
    if (uVar9 == 0) break;
    uVar9 = uVar9 - 1;
    cVar4 = *pcVar12;
    pcVar12 = pcVar12 + 1;
  } while (cVar4 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)&pcStack_18,(undefined4 *)s_Redman_0063cac8,~uVar9 + 0x63cac7);
  iVar6 = dStack_14 - (int)pcStack_18;
  if (iVar6 == (int)ppbVar3[1] - (int)*ppbVar3) {
    bVar16 = true;
    pcVar11 = pcStack_18;
    pbVar10 = *ppbVar3;
    do {
      if (iVar6 == 0) break;
      iVar6 = iVar6 + -1;
      bVar16 = *(byte *)&pcVar11->~cls_0x6354e4_0 == *pbVar10;
      pcVar11 = (cls_0x6354e4::vftable_6354e4 *)((int)&pcVar11->~cls_0x6354e4_0 + 1);
      pbVar10 = pbVar10 + 1;
    } while (bVar16);
    if ((!bVar16) || (**(char **)(param_1[0x4a] + 0x98) != 'm')) goto LAB_004f7d8c;
    bVar16 = true;
  }
  else {
LAB_004f7d8c:
    bVar16 = false;
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&pcStack_18);
  if (bVar16) {
    cVar4 = (**(code **)(*(int *)param_1[0x4a] + 0x1c))(&DAT_00638700);
    this_01 = (cls_0x61922d *)(-(uint)(cVar4 != '\0') & (uint)param_1);
    puVar1 = &this_01[3].field_0x34;
    *puVar1 = *puVar1 | 0x20;
    OOAnalyzer::cls_0x61922d::meth_0x61922d(this_01);
  }
LAB_004494b5:
  if (DAT_00638154 == (undefined *)0x0) {
    DAT_00638154 = &LAB_00441880;
  }
  if (DAT_00638589 == '\0') {
    piVar5 = (int *)OOAnalyzer::cls_0x449560::meth_0x449560
                              ((cls_0x449560 *)&DAT_00639040,(int *)&param_3,ppbVar3);
    iVar6 = *piVar5;
    iStack_1c = DAT_00639040;
    if (iVar6 != DAT_00639040) {
      ppcVar13 = (char **)(iVar6 + 0x1c);
      if (*(char *)(iVar6 + 0x50) != '\0') {
        piVar5 = (int *)OOAnalyzer::cls_0x40143b::meth_0x401000
                                  ((cls_0x40143b *)&DAT_00641860,&iStack_1c);
        iVar2 = *piVar5;
        piVar5 = (int *)OOAnalyzer::cls_0x40143b::meth_0x607b9a
                                  ((cls_0x40143b *)&DAT_00641860,(int *)&pcStack_18,ppbVar3);
        if (*piVar5 != iVar2) {
          return;
        }
      }
      if (((*(char **)(iVar6 + 0x20) == *ppcVar13) ||
          (uVar8 = FUN_0040da1d(ppcVar13,(char **)(param_1[0x4a] + 0x98)), (char)uVar8 != '\0')) &&
         ((*(char **)(iVar6 + 0x20) == *ppcVar13 ||
          (uVar8 = FUN_0040da1d((char **)(iVar6 + 0x28),(char **)(param_1[0x4a] + 0xa4)),
          (char)uVar8 != '\0')))) {
        OOAnalyzer::cls_0x40f018::meth_0x6089e8
                  (GLOBAL_ZOO_BUDGET_STATUS,(float)*(int *)(iVar6 + 0x34));
        FUN_0060875c(param_1,0,(char)*(undefined4 *)(iVar6 + 0x38));
        FUN_0060875c(param_1,1,(char)*(undefined4 *)(iVar6 + 0x3c));
        FUN_0060875c(param_1,2,(char)*(undefined4 *)(iVar6 + 0x40));
        this = DAT_00639010;
        if ((DAT_00639010 != (ZTResearchMgr *)0x0) &&
           (piVar5 = *(int **)(iVar6 + 0x44), piVar5 != *(int **)(iVar6 + 0x48))) {
          do {
            this_02 = (cls_0x404fd6 *)OOAnalyzer::ZTResearchMgr::meth_0x5944b6(this,*piVar5);
            if (this_02 != (cls_0x404fd6 *)0x0) {
              OOAnalyzer::cls_0x404fd6::meth_0x58fb83(this_02);
            }
            piVar5 = piVar5 + 1;
          } while (piVar5 != *(int **)(iVar6 + 0x48));
        }
        OOAnalyzer::cls_0x40143b::meth_0x607ab7((cls_0x40143b *)&DAT_00641860,&pcStack_18,ppbVar3);
      }
    }
  }
  return;
}

```

# XREFs

This function is only called from one location.

| Function Name | Function Location | Call Location | Access Type | Context |
| ---- | ---- | ---- | ---- | ---- |
| | 00449515 | 00449526 | (c) | Part of a greater class |
