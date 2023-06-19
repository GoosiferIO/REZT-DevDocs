# `ZTGameMgr::addToBudget(float deposit)`

This function is found at location `0040F018`--coincidentally, the same location as its parent class: [ZTGameMgr](ZTGameMgr.md). 

It adds to the existing budget on the visible UI. After the budget has been updated to memory, this function calls another:  [ZTGameMgr::0x0040EE3D](ZTGameMgr%200040EE3D.md). It is not clear what this local function call is doing.

# Decompile

Below is a rough decompile from Ghidra:

```C++
void __thiscall OOAnalyzer::cls_0x40f018::meth_0x40f018(cls_0x40f018 *this,float param_1)

{
  *(float *)&this->field_0xc = param_1 + *(float *)&this->field_0xc;
  FUN_0040ee3d();
  return;
}
```


# XREFs

The following is a table listing all of the calls to the `addToBudget` function in the assembly code. The second column is the address to the function where it is called, third column is the location of the `addToBudget` call within that function, and the fourth column is the context of that call (what triggers this call). This mapping will help us identify what the functions in the first column are doing.

| Call Num | Calling Function | addToBudget Location | Calling Function Context |
| --- | ----- | ---------- | ---------|
| 1 | `00613e4a` | `00613f61` | |
| 2 | `0060d8e3` | `0060d9d3` | |
| 3 | `0060ccc2` | `0060cccd` | |
| 4a* | `004f94be` | `0050A245` | Called when selling animal, vending machine. Has a label: 0050a242. Todo for 4a and 4b: test all sellable animals, objects. Do they all trigger this function? |
| 4b* | `0050a0b0` | `0050a245` | Called when selling animal, vending machine. Has a label: 0050a242. | 
| 5 | `006089e8` | `006089fc` | Adds $20,000 when renaming a male Zookeeper Jonathan Gilmour with .cfg file |
| 6 | `00607174` | `00607299` | 
| 7 | `005b0f17` | `005b0f2d` | Sets the budget for a new zoo from the main menu | 
| 8 | [005A13C5](00635510%20005A13C5.md) | `005a1679` | Adds $10,000 when cash is less than $1000 (normal map), adds $500,000 when cash is less than $25,000 (MM:kiddie map, medium) |
| 9 | `004f6e3c` | `004f7031` | Updates budget when guest pays admission |
| 10 | `004d9088` | `004d920f` | Undo after a destroy or purchase - restores budget to previous state |
| 11 | `004a2c98` | `004a2f97` | |
| 12 | `00483f11` | `00484047` | Called every month to pay staff salary |
| 13 | `0042ec49` | `0042ec81` | Unknown: Could be donations or benefactors? Triggers every few seconds, not sure what is being added or subtracted from budget. Values observed: 0.018, 0.013, 0.457, 0.406. |
| 14 | `0042d858` | `0042d93f` | Adds to budget when guest makes a purchase. Values observed: 2.00, 2.00, 2.00, 2.50. Buildings observed: Stands, vending machines, arcades. Todo: test other buildings. Interesting observation: A single payment is actually double the price you set. Ex: If you set to 1.25, you actually get paid 2.50. |
| 15 | `0042ce0a` | `005a981c` | Dolphin show ticket purchase |
\* *4a and 4b are called inside of the same structure. Unclear how this works or what that structure looks like.*

## Recent developments concerning this table:

- **06/18/2023**:  [005A13C5](00635510%20005A13C5.md) is a function that belongs to a class at [00635510](00635510.md). It appears to have functionality concerning .scn file parsing and the logic handling involved in their settings.