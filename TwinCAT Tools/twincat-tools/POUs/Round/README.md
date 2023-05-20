# Round Functions

The `F_ROUNDREAL` function is a custom function in TwinCAT that allows you to round a real number to a specified number of decimal places.

## Function Signature

```pascal
FUNCTION F_ROUNDREAL : REAL
VAR_INPUT
    rValue      : REAL;  // Input Value
    iDecNumber  : INT;   // Numbers after decimal point
END_VAR
VAR
    rOutValue   : REAL;
END_VAR

rOutValue := rValue * EXPT(10,iDecNumber);
rOutValue := TRUNC(rOutValue) / EXPT(10,iDecNumber);
F_ROUNDREAL := rOutValue;
```

## Input Parameters
- rValue (Input): The real number that you want to round.
- iDecNumber (Input): The number of decimal places to round to.

## Return Value
- F_ROUNDREAL returns a REAL value that represents the rounded result of the input number with the specified decimal places.

## Usage Example

```pascal
VAR
    MyValue : REAL := 3.14159;
    RoundedValue : REAL;
END_VAR


RoundedValue := F_ROUNDREAL(MyValue, 2);  // Round MyValue to 2 decimal places
```

In this example, the MyValue variable represents the real number that you want to round. The F_ROUNDREAL function is then used to round MyValue to 2 decimal places. The result is stored in the RoundedValue variable.

After executing the code, RoundedValue will contain the rounded value of MyValue with 2 decimal places.

# Feel free to modify and format the documentation according to your specific needs.
