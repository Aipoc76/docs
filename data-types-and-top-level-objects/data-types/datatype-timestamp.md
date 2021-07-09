# DataType:timestamp

A timestamp represented in milliseconds.

| **Type** | **Member** | **Description** |
| :--- | :--- | :--- |
| [_int_](datatype-int.md) | **Hours** | Number of hours remaining in the timestamp \(1hr 23min 53 seconds will return 1\) |
| [_int_](datatype-int.md) | **Minutes** | Number of Minutes remaining in the timestamp \(1hr 23min 53 seconds will return 23\) |
| [_int_](datatype-int.md) | **Seconds** | Number of Seconds remaining in the timestamp \(1hr 23min 53 seconds will return 53\) |
| [_string_](datatype-string.md) | **TimeHMS** | Remaining Time value formatted in H:M:S |
| [_string_](datatype-string.md) | **Time** | Remaining  Time value formatted in M:S |
| [_int_](datatype-int.md) | **TotalMinutes** | Total number of remaining minutes in the timestamp \(1hr 23min 53 seconds will return 83\) |
| [_int_](datatype-int.md) | **TotalSeconds** | Total number of remaining minutes in the timestamp \(1hr 23min 53 seconds will return 5033\) |
| [_int_](datatype-int.md) | **Raw** | Remaining time value represented in milliseconds |
| [_float_](datatype-float.md) | **Float** | timestamp represented in remaining seconds \(1hr 23 min 53 seconds will return 5033.00\) |
| [_int_](datatype-int.md) | **Ticks** | Remaining time value represented in ticks |
| \_\_[_string_](datatype-string.md)\_\_ | **To String** | Same as **Raw** |



