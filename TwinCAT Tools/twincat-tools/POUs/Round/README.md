# Round Functions

The `F_ROUND_REAL` function is a custom function in TwinCAT that allows you to round a real number to a specified number of decimal places.

## Function Signature

```pascal
FUNCTION F_ROUND_REAL : REAL
VAR_INPUT
    rValue      : REAL;  // Input Value
    iDecNumber  : INT;   // Numbers after decimal point
END_VAR
VAR
    rOutValue   : REAL;
    rLeftValue	: REAL;
END_VAR

rOutValue := rValue * EXPT(10,iDecNumber);
rLeftValue := rOutValue - TRUNC(rOutValue);
IF rLeftValue >= 0.5 THEN
	rOutValue := TRUNC(rOutValue + 1) / EXPT(10,iDecNumber);
ELSE
	rOutValue := TRUNC(rOutValue) / EXPT(10,iDecNumber);
END_IF
F_ROUND_REAL := rOutValue;
```

## Input Parameters
- rValue (Input): The real number that you want to round.
- iDecNumber (Input): The number of decimal places to round to.

## Return Value
- F_ROUND_REAL returns a REAL value that represents the rounded result of the input number with the specified decimal places. It rounds to higher number if the lef value is bigger or equal than 0.5.

## Usage Example

```pascal
VAR
    MyValue : REAL := 3.14159;
    RoundedValue : REAL;
END_VAR


RoundedValue := F_ROUND_REAL(MyValue, 2);  // Round MyValue to 2 decimal places - Rounded value = 3.14
```

In this example, the MyValue variable represents the real number that you want to round. The F_ROUND_REAL function is then used to round MyValue to 2 decimal places. The result is stored in the RoundedValue variable.

After executing the code, RoundedValue will contain the rounded value of MyValue with 2 decimal places.
