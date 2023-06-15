This class appears to update many of the UI elements on the screen. As of this moment, only functionality related to the budget has been exposed in this class, but we speculate that there may be other member functions. It might make sense to see this class as the 'player state' class.

This class is located at `0x0040F018`.

# Table of Contents

[[#Structure]]
1. [[#addToBudget(float &budget)]]
	1. [[#All calls to addToBudget(..)]]
2. [[#jonathanGilmourTribute(float &budget)]]
	1. [[#skeeper04.cfg]]
	2. [[#Attributes]]
	3. [[#Other usage]]
	4. [[#Other cheat functions]]

## Structure

| Member | Description | Location |
| ------- | --------------- | ---------|
| budget | Stores the value of the budget on the game screen | `*(zoo.exe + 0x00238048) + 0x0C`  |
| subtractFromBudget(..) | Subtract from the budget | `*(zoo.exe + 0x41ef68)` |
| [[#addToBudget(float &budget)]] | Adds to the budget | `*(zoo.exe + 0x0040F018)` |
| [[#jonathanGilmourTribute(float &budget)]]| Adds $20,000 to the budget, 23321 points to research, among a few other .cfg-related settings | `*(zoo.exe + 0x006089E8)`|

## `addToBudget(float &budget)`

The first function we've exposed. This function adds to the existing budget on the screen. After the budget has been updated to memory, this function calls another at location `*(zoo.exe + 0x006089E8)`. It is not clear what this local function call is doing yet outside of listening for the budget to drop to $0. 

### All calls to `addToBudget(..)`

The following is a table with all of the calls to the `addToBudget(..)` function in the assembly code. First column is the address to the function where it is called, second row is the location of the `addToBudget` call within that function, and the third column is the context of that call (what triggers this call). This mapping will help us identify what the functions in the first column are doing.

If it's linked it means that function has been identified and will lead you to its definition.

| Call Num | Calling Function | addToBudget Location | Calling Function Context |
| --- | ----- | ---------- | ---------|
| 1 | 00613e4a | 00613f61 | |
| 2 | 0060d8e3 | 0060d9d3 | |
| 3 | 0060ccc2 | 0060cccd | |
| 4a* | 004f94be | 0050A245 | Called when selling animal, vending machine. Has a label: 0050a242. Todo for 4a and 4b: test all sellable animals, objects. Do they all trigger this function? |
| 4b* | 0050a0b0 | 0050a245 | Called when selling animal, vending machine. Has a label: 0050a242. | 
| 5 | 006089e8 | 006089fc | Adds $20,000 when renaming a male Zookeeper Jonathan Gilmour with .cfg file |
| 6 | 00607174 | 00607299 | 
| 7 | 005b0f17 | 005b0f2d | Sets the budget for a new zoo from the main menu | 
| 8 | 005a13c5 | 005a1679 | Adds $10,000 when cash is low |
| 9 | 004f6e3c | 004f7031 | Updates budget when guest pays admission |
| 10 | 004d9088 | 004d920f | Undo after a destroy or purchase - restores budget to previous state |
| 11 | 004a2c98 | 004a2f97 | |
| 12 | 00483f11 | 00484047 | Called every month to pay staff salary |
| 13 | 0042ec49 | 0042ec81 | Unknown: Could be donations or benefactors? Triggers every few seconds, not sure what is being added or subtracted from budget. Values observed: 0.018, 0.013, 0.457, 0.406. |
| 14 | 0042d858 | 0042d93f | Adds to budget when guest makes a purchase. Values observed: 2.00, 2.00, 2.00, 2.50. Buildings observed: Stands, vending machines, arcades. Todo: test other buildings. Interesting observation: A single payment is actually double the price you set. Ex: If you set to 1.25, you actually get paid 2.50. |
| 15 | 0042ce0a | 005a981c | |
\* *4a and 4b are called inside of the same structure. Unclear how this works or what that structure looks like.*

## `jonathanGilmourTribute(float &budget)`

### skeeper04.cfg

This function is a cheat function. It adds $20,000 to the zoo budget when a male zookeeper is named "Jonathan Gilmour". In order for this function to activate, a file originally distributed by Blue Fang named `skeeper04.cfg` needs to be saved in the `Zoo Tycoon/dlupdate` folder. This is a simple text file with the following contents:

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

### Attributes

It's also adding research points, setting colors, among other attributes. However, outside of `addresearch`, `bonuscash`, `type`, and `oneTimeBonus` attributes, it's not clear what the other ones are doing. 

It seems to be parsing the configuration file and setting these attributes to values in virtual memory using a local function call at location `*(zoo.exe + 0x0042EBBE)`. However, not a lot of time has been dedicated to reversing this function, so it's not clear what it's doing exactly. Below are functions that seem to call it, so it's used again in other areas of the code. It also appears to be part of a greater class, however that class has not yet been discovered, hence why documentation for it will sit here for now. However, unlike `addToBudget`, none of these have been mapped yet:

```

FUN_0042ec49:0042ec79(c), 0046bc5c(c), FUN_005a13c5:005a1671(c), FUN_006089e8:006089f4(c), FUN_0060d8e3:0060d9c7(c), FUN_00613e4a:00613f59(c), 00616bf2(c)
```

### Other usage

Many mods have used skeepr04.cfg by changing the attributes within to create their own cheat. Because no efforts to reverse engineer the game have been made, all of these cheat mods do the same thing in the end. They all add to the budget, and modify the same attributes listed above.

This function is only called once, so its purpose is clear.

### Other cheat functions

This function is only called once, and this is how the cheat function was discovered. For more information on that cheat function, please see [[Global Functions]].