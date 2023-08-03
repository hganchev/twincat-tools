### F_STRINGSPLIT Function
This function takes a string sInput and a split character sSplitChar and splits the input string into an array of substrings. The resulting array, F_STRINGSPLIT, has a size of Parameters.iSplitArraySize.

## Inputs
sInput (STRING): The input string to be split. It has a maximum length of 255 characters.
sSplitChar (STRING): The character used to split the input string. It should be a single character.
## Outputs
F_STRINGSPLIT (ARRAY[0..Parameters.iSplitArraySize] OF STRING(255)): The array of substrings resulting from the split operation. Each substring has a maximum length of 255 characters.
Implementation
The function implementation is as follows:

```pascal
sCopy := sInput;

FOR i := 0 TO Parameters.iSplitArraySize DO
	IF FIND(sCopy, sSplitChar) > 0 THEN
		sSplit := LEFT(sCopy, FIND(sCopy, sSplitChar) - 1);
		iDeleteLen := LEN(sSplit) + LEN(sSplitChar);
	ELSE
		sSplit := sCopy;
		iDeleteLen := LEN(sSplit);
	END_IF
	
	// Take the string value
	F_STRINGSPLIT[i] := sSplit;
	
	// Delete 
	sCopy := DELETE(sCopy, iDeleteLen, 1);
	
	// End of split
	IF sCopy = '' THEN
		EXIT;
	END_IF
END_FOR
```
This implementation iteratively splits the input string using the specified split character. It assigns each substring to the corresponding element in the F_STRINGSPLIT array. The splitting process continues until either the end of the input string is reached or the maximum number of substrings specified by Parameters.iSplitArraySize is reached.

Note: The code provided is written in a pseudocode-like syntax. Please adapt it to the specific programming language you are using before incorporating it into your project.
