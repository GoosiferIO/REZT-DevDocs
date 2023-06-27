Return to [start here](../start%20here.md) / [API Code](../General/API%20Code.md)

# `EmuConsole`

One of the core features for this API is the command console. A lot of the debugging and testing of reversed functions and classes will utilize it. Though not designed for the average user to use, it is still accessible to anyone that wants it.

# Table of Contents

[[#Usage]]
   [[#Opening the Console]]
   [[#Closing the Console]]
   [[#Available Commands]]
[Limitations](#Limitations)
[Code Structure](#Code%20Structure)
   [[#Member Types]]
   [[#Member Functions]]
[[#Changelog]]

# Usage

## Opening the Console

The command console is accessible by typing in the command `CTRL + J` while the game is running. A few things to keep in mind for now:

- In order to view the console, it is recommended that the game be in windowed mode.
- It is also recommended to hold off on opening the console until after the loading bar is done loading. This is where the game allocates the memory it needs for the [[ZTGameMgr]] object. At the moment, the console makes use of it.
	- A planned safety check for the future will allow the console to open, but will not allow any commands to run until this memory space has been allocated.

## Closing the Console

The console can be closed by entering the `exit` command. This will allow you to safely close the command console window without forcing the main game to close as well.

## Available Commands

> [!Note]
> After the console rewrite, `addtobudget` was removed.  `addtobudget` along with 20 other commands will be available in the console before first release in July. These commands will be in the console as a proof of concept and to stress test the console, and not for their utility (most are just zoo stats). In the future, implemented commands will be programmed in with their utility in mind.

| Member Function | Definition |
|---- | ---- |
| exit | Exits the game |
| pause | Pause the game |
| play | Play the game |

# Limitations

- **Safety Checks** | In need of safety checks in case a user enters unexpected input.

# Code Structure

```C++ 
class EmuConsole
{
public:
    EmuConsole();
    void processInput(bool&);
    ~EmuConsole();

private:
    void tokenize();
    std::vector<std::string> tokens;
};
```

## Member Types

| Member Function | Definition |
|---- | ---- |
| tokens | A list of tokens provided by the user. |

## Member Functions

| Member Function | Definition |
|---- | ---- |
| ProcessInput | Initializes a console window and delegates user-input to the corresponding functions and arguments. |
| Tokenize | Tokenize user input. |

# Changelog

- ***06/25/2023*** `exit` command closes console attachment to thread. Still requires manual closing of console window though.
- ***06/25/2023*** Console thread is closed at bootup.`CTRL + J` opens the console and thread.
- ***06/25/2023*** Console now runs on its own thread (to prevent deadlock in main loop)
- ***06/25/2023*** Added `pause` and `play` commands to the console
- ***06/23/2023*** Implemented `tokenize()` function
- ***06/23/2023*** Cleaned up `EmuConsole::processInput`
- ***06/23/2023*** Refactored console code so that it's cleaner