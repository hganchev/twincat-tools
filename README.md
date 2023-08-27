# twincat-tools
TwinCAT tools for better programming 

- [Toools](https://github.com/hganchev/twincat-tools/tree/main/TwinCAT%20Tools/twincat-tools/POUs)
- [Examples](https://github.com/hganchev/twincat-tools/tree/main/TwinCAT%20Tools/twincat-tools/Examples)
- [Library](https://github.com/hganchev/twincat-tools/tree/main/library)

## Installation
Download [library file](https://github.com/hganchev/twincat-tools/tree/main/library) then in TwinCAT project go to References -> Library Repository -> Install -> find the library file and click Open.

![](https://github.com/hganchev/twincat-tools/blob/main/library/Install_Library.PNG)

## Usage
```pascal
VAR
	roundValue 		: LREAL;
END_VAR

roundValue = F_ROUND_LREAL(5.22222222, 2); // Round value to second sign
```
