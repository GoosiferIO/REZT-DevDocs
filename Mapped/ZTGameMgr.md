Return to [start here](../start%20here.md) / [Mapped Code](../General/Mapped%20Code.md)

# `ZTGameMgr`

This class appears to update many of the UI elements on the screen. As of this moment, only functionality related to the budget has been exposed in this class, but we speculate that there may be other member functions. It might make sense to see this class as the 'player state' class.

At this time, it might seem that the class exists at `0x0040F018`, but an instantiated form is found at this pointer: `0x00638048`.

`ZTGameMgr` extends all of the way to offset `0x11B0`.

# Table of Contents

[[#Structure]]
	[Data Members](#Data%20Members)
	[Need More Testing](#Need%20More%20Testing)
	[Class Functions](#Class%20Functions)

# Structure

## Data Members

The following offsets are added to the `*(0x638048)` pointer.

| Member |  Offset | Data Type | Member Type | Description | 
| ------- | --------------- | ---------| -----| ---- |
| `ZooBudget` | `0x0C`  | float | Variable | Stores the value of the budget on the game screen |
| `NumAnimals` | `0x30` | int | Variable | Number of animals in the zoo |
| `NumExhibits` | `0x38` | int | Variable | Number of exhibits in the zoo |
| `NumGuests` | `0x54` | int | Variable | Number of guests in the zoo |
| `AdmissionsIncomeByMonth[12]` | `0x254` | float | Array | Stores admission income by month. Every element counts as one month. |
| `ConcessionsBenefitByMonth[12]` | `0x29C` | float | Array | Stores concession benefit values by month. |
| `RecyclingBenefitByMonth[12]` | `0x340` | float | Array | Stored recycling benefit values by month. |
| `ZooProfitOverTime[12]` | `0x404` | float | Array | Stores zoo profit over the course of 12 months. |
| `IncomeExpenseTotalsByMonth[12]` | `0x44C` | float | Array | Stores income expense totals by month |
| `ZooRatingByMonth[12]` | `0x464` | float | Array | Calculated as the game runs, not at end of month |
| `ContructionCostByMonth[12]` | `0x824` | float | Array | Stores construction costs by month. |

## Need More Testing

The following need more testing to make sure they stay consistent across saves.

| Member |  Offset | Data Type | Member Type | Description | 
| ------- | --------------- | ---------| -----| ---- |
| `NumAngryGuests` | `0x38`  | int | Variable | How many angry guests in zoo |
| `NumTiredGuests` | `0x3C` | int | Variable | How many tired guests in zoo |
| `NumHungryGuests` | `0x30` | int | Variable | How many hungry guests in zoo |
| `NumThirstyGuests` | `0x44` | int | Variable | How many thirsty guests in zoo |
| `NumGuestsNeedRestrm` | `0x48` | int | Variable | How many guests in zoo need to use the loo. |
| `NumGuestsInFilter` | `0x50` | int | Variable | This is effectively the total number of guests in the zoo, but specific to the filter dialog, it's in reference to how many guests are in the filter. |
| `ZooAdmissionCost` | `0x1150` | float | Variable | Admission cost for an adult ticket to enter the zoo. Child ticket is a calculated value divided by half. |
| `ZooValueOverTime[12]` | `0x434` | float | Array | Zoo value over time. This one is cool because it's not available in the game. |

## Data Types Possibly Identified But Purpose Unknown

We have a rough idea of what the data types for the following resources are, but have not identified their purpose.

| Member |  Offset | Data Type | Member Type | Description | 
| ------- | --------------- | ---------| -----| ---- |
| ---- | `0x10`  | int | Variable | Seems to always have the value 4,000 across saves |
| ---- | `0x3C` | int | Variable | Seems to always have the value 10,000 across saves |
| ---- | `0x18` | int | Variable | Seems to always have the value 2,000 across saves |
| ---- | `0x04` | string? | Variable | Often stores the string value 'sfguide.pal'. Sometimes not there on some loads. |
| `Unknown[12]` | `0x4C4` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x3D4` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x4F4` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x524` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x554` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x584` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x5B4` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x5E4` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x644` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x674` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |
| `Unknown[12]` | `0x6A4` | float | Array | Array of unknown purpose. 48 bytes, 12 members. |

# Class Functions 

At the moment the following functions are speculative and are originally defined in the `0x0040F018` class. However, if we can find evidence that  the `0x00638048` pointer is an instantiated form of this class, these are also part of it. 

| Member |  Location | Ret Type | Member Type | Description | 
| ------- | --------------- | ---------| -----| ---- |
| [subtractFromBudget](ZTGameMgr%20subtractFromBudget%200041EF68.md) | `0041EF68` | void | function | Subtract from the budget |
| [addToBudget](ZTGameMgr%20addToBudget%200040F018.md) | `0040F018` | void | function | Adds to the budget |
| [jonathanGilmourTribute](ZTGameMgr%20jonathanGilmourTribute%20006089E8.md) | `006089E8` | void | function | Adds $20,000 to the budget, 23321 points to research, among a few other .cfg-related settings |
| [0040EE3D](ZTGameMgr%200040EE3D.md) | `0040EE3D` | unknown | function | This function is called inside of addToBudget and subtractFromBudget. Not much else is known. |