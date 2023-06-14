# **API Code**

Category name might change. Code below is related to code functional to the API features only.

**Command Console**

It isn't clear if the game has its own command console, but there seem to be traces here and there that might suggest there is or was. Since this feature is important to test hooked functions and rewritten code, I decided to make one.

- [EmuConsole](../API/EmuConsole.md)

**Mod Loading**

The API will require mod loading for mods that utilize our features. This code was contributed by gurrenm4 in the earlier parts of the project. Needs a lot of modification since it's a rough port from C# to C++, so at the moment it has been commented out in the repo. Mod loading isn't important right now until the API has more game code to draw from.

- EmuController
- EmuGameLoop
- EmuLoader
- EmuMod

**Utilities**

Utilities will mainly house the hooking functions and other functions vital to reading virtual memory. They still have the old prefixes from the previous name of the project. That will be updated later.

- TekMemory
- TekUtilities