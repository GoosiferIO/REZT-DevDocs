`main(..)` is located at `0x004CBDF6`. Unclear if this is the main game loop or if another function owns that role. What seems clear is that this is handling many of the game's message management so it very well might be functioning as the message loop.

## Signature

The function signature is speculative and the only basis this draws from is from decompiler tools. Still, this is most likely correct.

```C++
int main(int argc, char **argv, char **envp);
```

## Future Plans

The intention eventually might be to hook onto one of the message functions within the main loop to inject thread-safe instructions. Ideally, these injected functions would be where the mods would run.