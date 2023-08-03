# F_IN_BOUNDS_ARRAY_INT Function

The `F_IN_BOUNDS_ARRAY_INT` function is a custom function in TwinCAT that checks if an index is within the bounds of an integer array.

## Function Signature

```pascal
FUNCTION F_IN_BOUNDS_ARRAY_INT : BOOL
VAR_INPUT
    index       : DINT;              // The index to check
END_VAR
VAR_IN_OUT
    arrayIn     : ARRAY[*] OF INT;   // The integer array to check against
END_VAR
```

# Parameters
`index` (Input): The index to check whether it is within the bounds of the array.
`arrayIn` (Input/Output): The integer array against which the index is checked.

# Return Value
`F_IN_BOUNDS_ARRAY_INT` returns a BOOL value. It is set to `TRUE` if the index is within the bounds of the array; 
otherwise, it is set to `FALSE`.

# Usage Example
```pascal
VAR
    MyArray : ARRAY[1..5] OF INT := [10, 20, 30, 40, 50];
    MyIndex : DINT := 3;
    IsInBounds : BOOL;
END_VAR

IsInBounds := F_IN_BOUNDS_ARRAY_INT(MyIndex, MyArray);
```
In this example, the `MyArray` variable represents an integer array with elements 
`[10, 20, 30, 40, 50]`. The `MyIndex` variable contains the index that you want to check. 
The `F_IN_BOUNDS_ARRAY_INT` function is then used to check whether `MyIndex` is within the bounds of `MyArray`. 
The result is stored in the `IsInBounds` variable.

After executing the code, `IsInBounds` will be set to `TRUE` since the value of `MyIndex (3)` is within the bounds of `MyArray`.