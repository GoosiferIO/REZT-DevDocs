## `jonathanGilmourTribute(float budget)`

This function is a cheat function. It adds $20,000 to the zoo budget when a male zookeeper is named "Jonathan Gilmour" among other attributes. It is located at `006089E8`.

Below is a rough decompile from Ghidra:

```C++
void __thiscall OOAnalyzer::cls_0x40f018::meth_0x6089e8(cls_0x40f018 *this,float param_1)

{
  cls_0x42ebbe::meth_0x42ebbe((cls_0x42ebbe *)&this->mbr_0x10,param_1);
  meth_0x40f018(this,param_1);
  return;
}
```

## skeeper04.cfg

 In order for this function to activate, a file originally distributed by Blue Fang named `skeeper04.cfg` needs to be saved in the `Zoo Tycoon/dlupdate` folder. This is a simple text file with the following contents:

```JSON
[Jonathan Gilmour]
type=keeper
subtype=m
oneTimeBonus=1
color0=2
color1=1
color2=1
bonuscash=20000
addresearch=23321
addresearch=23323
```

The name of this function is questionable, but what is clear at the moment is that it seems to have been created in anticipation of announcing a winner to the Ultimate Zookeeper Contest in 2000. The game shipped before the winner was announced, so it makes sense that this function was made so that it can read the name of a prospective winner among other attributes defined post-release from a configuration file (.cfg). The winner was a "Jonathan Gilmour".

## Attributes

It's also adding research points, setting colors, among other attributes. However, outside of `addresearch`, `bonuscash`, `type`, and `oneTimeBonus` attributes, it's not clear what the other ones are doing. 

It seems to be parsing the configuration file and setting these attributes to values in virtual memory using a local function call at location `*(zoo.exe + 0x0042EBBE)`. However, not a lot of time has been dedicated to reversing this function, so it's not clear what it's doing exactly. Below are functions that seem to call it, so it's used again in other areas of the code. It also appears to be part of a greater class, however that class has not yet been discovered, hence why documentation for it will sit here for now. However, unlike `addToBudget`, none of these have been mapped yet:

```

FUN_0042ec49:0042ec79(c), 
0046bc5c(c), 
FUN_005a13c5:005a1671(c), 
FUN_006089e8:006089f4(c), 
FUN_0060d8e3:0060d9c7(c), 
FUN_00613e4a:00613f59(c), 
00616bf2(c)
```

## Other usage

Many mods have used `skeepr04.cfg` by changing the attributes within to create their own cheat. Because no efforts to reverse engineer the game have been made, all of these cheat mods do the same thing in the end. They all add to the budget, and modify the same attributes listed above.

This function is only called once, so its purpose is clear.

## Other cheat functions

This function is only called once, and this is how the cheat function was discovered. For more information on that cheat function, please see [[Global Functions]].