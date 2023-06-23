Return to [start here](app://obsidian.md/start%20here.md) / [Mapped Code](app://obsidian.md/General/Mapped%20Code.md)

# `ZTAIMgr`

Not much known about how this class works yet, but as its namesake suggests, it is dealing with the game AI. We know its name because we have been able to map symbols with their pointers using a function that calls [[BFRegistry]].

The class constructor is at `0x0063536C`.

# Table of Contents

[[#Structure]]
   [[#Class Functions]]

# Structure

## Class Functions

These are the only known functions part of this structure at this time.

|Member|Location|Ret Type|Member Type|Description|
|---|---|---|---|---|
||`*(00638098) + 8`|void|member function|It's possible that this is a virtual function. Not much info given by Ghidra, will need other tools to verify.|