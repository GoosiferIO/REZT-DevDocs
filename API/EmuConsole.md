Return to [start here](../start%20here.md) / [API Code](../General/API%20Code.md)

# `EmuConsole`

One of the core features for this API is the command console. A lot of the debugging and testing of reversed functions and classes might utilize it.

# Table of Contents

[Limitations](#Limitations)
[Code Structure](#Code%20Structure)

# Limitations

- **Launching the Console** | Right now the code is fairly primitive and launches automatically with the game side-by-side. Plans are to eventually enable/disable the console by shortcut and within the game viewport. Until then, it requires windowed mode to be visible and usable.
- **Commands** | Only one command is usable right now while the focus of the project has been less on reversing code and more on core API features. Recent progress will soon allow for around 20 new commands to be added to the console as a proof of concept.
- **Safety Checks** | In need of safety checks in case a user enters unexpected input.

# Code Structure

```C++ 
class EmuConsole
{
public:
	EmuConsole(void);
	std::string tokenize(std::string);

	std::vector<std::string> tokens;
	void processInput(Zoo::Process p, Memory<float> w);
	~EmuConsole(void);
};
```

More documentation to come as the defined code for EmuConsole is revamped.