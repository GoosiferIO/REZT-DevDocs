# `main` `

`main(..)` is located at `0x004CBDF6`. Unclear if this is the main game loop or if another function owns that role. What seems clear is that this is handling many of the game's message management so it very well might be functioning as the message loop.

# Table of Contents

[Decompile](#Decompile)
[Signature](#Signature)
[Future Plans](#Future%20Plans)

# Decompile

Below is a rough Ghidra decompile:

```C++
WPARAM FUN_0041a8bc(undefined4 param_1,undefined4 param_2,undefined4 param_3)

{
  WPARAM WVar1;
  char cVar2;
  int iVar3;
  uint **ppuVar4;
  LSTATUS LVar5;
  BOOL BVar6;
  uint uVar7;
  undefined4 *unaff_EBX;
  char *pcVar8;
  undefined4 uStack_190;
  undefined auStack_18c [24];
  undefined auStack_174 [16];
  undefined auStack_164 [8];
  dword dStack_15c;
  WPARAM aWStack_158 [8];
  undefined auStack_138 [312];
  
  auStack_174._8_4_ = FUN_004bc0c7((int *)0x0);
  FUN_0053833a((int *)(auStack_174 + 8));
  if (DAT_00638154 == (undefined *)0x0) {
    DAT_00638154 = &LAB_00441880;
  }
  DAT_00638590 = param_2;
  aWStack_158[0] = 0x104;
  OOAnalyzer::cls_0x6354e4::meth_0x404cf4
            ((cls_0x6354e4 *)auStack_18c,(int)&uStack_190 + 3,(uint *)&DAT_00000008);
  auStack_164._0_4_ = (cls_0x6354e4::vftable_6354e4 *)0x0;
  *(undefined *)auStack_18c._4_4_ = 0;
  auStack_164._4_4_ = (HWND)0x0;
  dStack_15c = 0;
  uVar7 = 0xffffffff;
  pcVar8 = s_regkey_0064aa28;
  do {
    if (uVar7 == 0) break;
    uVar7 = uVar7 - 1;
    cVar2 = *pcVar8;
    pcVar8 = pcVar8 + 1;
  } while (cVar2 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)auStack_164,(undefined4 *)s_regkey_0064aa28,
             (int)(s_startup_0064aa20 + ~uVar7 + 7));
  auStack_174._0_4_ = (cls_0x6354e4::vftable_6354e4 *)0x0;
  auStack_174._4_4_ = 0;
  auStack_174._8_4_ = 0;
  uVar7 = 0xffffffff;
  pcVar8 = s_startup_0064aa20;
  do {
    if (uVar7 == 0) break;
    uVar7 = uVar7 - 1;
    cVar2 = *pcVar8;
    pcVar8 = pcVar8 + 1;
  } while (cVar2 != '\0');
  OOAnalyzer::cls_0x6354e4::meth_0x401a94
            ((cls_0x6354e4 *)auStack_174,(undefined4 *)s_startup_0064aa20,~uVar7 + 0x64aa1f);
  ppuVar4 = (uint **)FUN_0041b4bc((undefined4 *)auStack_138,(LPCSTR *)auStack_174,
                                  (LPCSTR *)auStack_164,(LPCSTR *)&DAT_006462d8);
  if (ppuVar4 != (uint **)auStack_18c) {
    OOAnalyzer::cls_0x6354e4::meth_0x404c52
              ((cls_0x6354e4 *)auStack_18c,*ppuVar4,(undefined *)ppuVar4[1]);
  }
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)auStack_138);
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)auStack_174);
  OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)auStack_164);
  if ((undefined4 *)&stack0x00000000 != &DAT_006387a8) {
    OOAnalyzer::cls_0x6354e4::meth_0x404c52
              ((cls_0x6354e4 *)&DAT_0063861c,(uint *)auStack_18c._0_4_,
               (undefined *)auStack_18c._4_4_);
  }
  LVar5 = RegOpenKeyExA((HKEY)0x80000002,(LPCSTR)auStack_18c._0_4_,0,0x20019,
                        (PHKEY)(auStack_18c + 0x14));
  if (LVar5 == 0) {
    LVar5 = RegQueryValueExA((HKEY)auStack_18c._20_4_,s_AppPath_00643634,(LPDWORD)0x0,(LPDWORD)0x0,
                             auStack_138 + 0x38,aWStack_158);
    RegCloseKey((HKEY)auStack_18c._20_4_);
    if (LVar5 == 0) {
      SetCurrentDirectoryA(auStack_138 + 0x38);
    }
  }
  uVar7 = OOAnalyzer::cls_0x537333::meth_0x537ee3((cls_0x537333 *)&DAT_00638148);
  if (((char)uVar7 == '\0') ||
     (uVar7 = OOAnalyzer::cls_0x537333::meth_0x537333((cls_0x537333 *)&DAT_00638148),
     (char)uVar7 == '\0')) {
    (**(code **)(DAT_00638148 + 0x34))();
    FUN_00401a2f((undefined4 *)auStack_18c._0_4_,auStack_18c._8_4_ - auStack_18c._0_4_);
    return 0;
  }
  GetCPInfo(0,(LPCPINFO)&DAT_00638158);
  DAT_0063816c = 0x63815e;
  DAT_00638170 = 1 < DAT_00638158;
  (**(code **)(DAT_00638148 + 0x1c))(DAT_00638154);
  cVar2 = (**(code **)(DAT_00638148 + 0x20))(1,param_3);
  if (cVar2 == '\0') {
    (**(code **)(DAT_00638148 + 0x34))();
    OOAnalyzer::cls_0x404fd6::meth_0x4012ba((cls_0x404fd6 *)&stack0xfffffe68);
    return 0;
  }
  auStack_18c._0_4_ = DAT_00638610;
  do {
    while( true ) {
      while( true ) {
        while (BVar6 = PeekMessageA((LPMSG)(auStack_164 + 4),(HWND)0x0,0,0,0), BVar6 != 0) {
          BVar6 = GetMessageA((LPMSG)(auStack_164 + 4),(HWND)0x0,0,0);
          if (BVar6 == 0) {
            (**(code **)(DAT_00638148 + 0x34))();
            FUN_0057e084();
            WVar1 = aWStack_158[0];
            if (unaff_EBX != (undefined4 *)0x0) {
              if (0x80 < uStack_190 - (int)unaff_EBX) {
                FUN_00402629(unaff_EBX);
                return WVar1;
              }
              uVar7 = (uStack_190 - (int)unaff_EBX) - 1 >> 3;
              *unaff_EBX = (&DAT_00638000)[uVar7];
              (&DAT_00638000)[uVar7] = unaff_EBX;
            }
            return aWStack_158[0];
          }
          iVar3 = TranslateAcceleratorA
                            ((HWND)auStack_164._4_4_,(HACCEL)auStack_18c._0_4_,
                             (LPMSG)(auStack_164 + 4));
          if ((iVar3 == 0) &&
             (uVar7 = FUN_00418fdf((undefined4 *)(auStack_164 + 4)), (char)uVar7 == '\0')) {
            TranslateMessage((MSG *)(auStack_164 + 4));
            DispatchMessageA((MSG *)(auStack_164 + 4));
          }
        }
        if (DAT_006385ec == '\0') break;
        (**(code **)(DAT_00638148 + 0x30))();
      }
      if (*(char *)(DAT_00638050 + 4) == '\0') break;
LAB_0058c1c2:
      WaitMessage();
    }
    auStack_138._0_4_ = 0x2c;
    GetWindowPlacement(DAT_0063860c,(WINDOWPLACEMENT *)auStack_138);
    switch(auStack_138._8_4_) {
    case 0:
    case 2:
    case 6:
    case 7:
      goto LAB_0058c1c2;
    default:
      (**(code **)(DAT_00638148 + 0x30))();
      Sleep(0);
    }
  } while( true );
}
```

# Signature

The function signature is speculative and the only basis this draws from is from decompiler tools. Still, this is most likely correct considering most main drivers have a similar or identical signature.

```C++
int main(int argc, char **argv, char **envp);
```

# Future Plans

The intention eventually might be to hook onto one of the message functions within the main loop to inject thread-safe instructions. Ideally, these injected functions would be where the mods would run.