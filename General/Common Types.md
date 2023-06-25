Return to [start here](../start%20here.md) / [Mapped Code](Mapped%20Code.md) 

# Common Types
## ZT String

^a0e4e3

Strings are represented with 3 uint pointers. The first pointer references the first character of the string. The second pointers references the the null byte at the end of the string. The last pointer references the end of the string buffer.
## ZT Array
Similar to strings these are stored as 3 uint pointers, the first references the first element, the second references the byte after the last element, the third references the end of the buffer (this is an assumption)