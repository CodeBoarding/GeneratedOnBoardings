```mermaid
graph LR
    round_df["round_df"]
    get_num_decimal_places["get_num_decimal_places"]
    round_df -- "calls" --> get_num_decimal_places
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20codeboarding@gmail.com-lightgrey?style=flat-square)](mailto:codeboarding@gmail.com)

## Component Details

The Data Rounding component focuses on providing a mechanism to round numerical data within Pandas DataFrames to a specified precision. This ensures data consistency and facilitates easier analysis by controlling the number of decimal places. The core functionality revolves around the `round_df` function, which iterates through DataFrame columns, identifies numeric ones, and applies rounding based on the `get_num_decimal_places` function.

### round_df
This function rounds a Pandas DataFrame to a specified number of decimal places. It iterates through the columns of the DataFrame and applies rounding to numeric columns. It uses the `get_num_decimal_places` function to determine the number of decimal places to round to for each column.


**Related Classes/Methods**:

- <a href="https://github.com/meteomatics/python-connector-api/blob/master/meteomatics/rounding.py#L162-L168" target="_blank" rel="noopener noreferrer">`meteomatics.rounding:round_df` (162:168)</a>


### get_num_decimal_places
This function determines the number of decimal places to round to based on the data type of the input. If the input is a float, it calculates the number of decimal places. If it's not a float, it returns 0. This function is used by `round_df` to determine the appropriate precision for rounding.


**Related Classes/Methods**:

- <a href="https://github.com/meteomatics/python-connector-api/blob/master/meteomatics/rounding.py#L64-L159" target="_blank" rel="noopener noreferrer">`meteomatics.rounding:get_num_decimal_places` (64:159)</a>