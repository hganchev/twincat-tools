# F_GET_IN_RANGE_INT Function

The `F_GET_IN_RANGE_INT` function is a custom function in TwinCAT that allows you to map an input 
integer value from one range to another range.

## Function Signature

```pascal
FUNCTION F_GET_IN_RANGE_INT : INT
VAR_INPUT
    value       : INT;  // Input value to map
    range_max   : INT;  // Maximum value of the target range
    range_min   : INT;  // Minimum value of the target range
    value_max   : INT;  // Maximum value of the input value range
    value_min   : INT;  // Minimum value of the input value range
END_VAR
VAR
END_VAR
```

# Parameters
- `value` (Input): The input integer value that you want to map to the target range.
- `range_max` (Input): The maximum value of the target range.
- `range_min` (Input): The minimum value of the target range.
- `value_max` (Input): The maximum value of the input value range.
- `value_min` (Input): The minimum value of the input value range.

# Return Value
`F_GET_IN_RANGE_INT` returns an `INT` value that represents the mapped integer value from the input range to the target range.

# Usage Example
```pascal
VAR
    InputValue : INT := 50;
    MappedValue : INT;
END_VAR

// Map InputValue from the range [0, 100] to the range [500, 1000]
MappedValue := F_GET_IN_RANGE_INT(InputValue, 1000, 500, 100, 0);
```
In this example, the `InputValue` variable represents the integer value that you want to map. The `F_GET_IN_RANGE_INT` 
function is then used to map InputValue from the range `[0, 100]` to the range `[500, 1000]`. 
The result is stored in the MappedValue variable.

After executing the code, MappedValue will be equal to `750`.