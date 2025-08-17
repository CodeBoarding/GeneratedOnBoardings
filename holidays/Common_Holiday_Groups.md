```mermaid
graph LR
    holidays_groups_christian["holidays.groups.christian"]
    holidays_groups_islamic["holidays.groups.islamic"]
    holidays_groups_chinese["holidays.groups.chinese"]
    holidays_groups_hebrew["holidays.groups.hebrew"]
    holidays_groups_hindu["holidays.groups.hindu"]
    holidays_groups_balinese_saka["holidays.groups.balinese_saka"]
    holidays_groups_buddhist["holidays.groups.buddhist"]
    holidays_groups_mandaean["holidays.groups.mandaean"]
    holidays_groups_mongolian["holidays.groups.mongolian"]
    holidays_groups_persian["holidays.groups.persian"]
    holidays_holiday_base_HolidayBase["holidays.holiday_base.HolidayBase"]
    holidays_countries["holidays.countries"]
    holidays_calendars["holidays.calendars"]
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_christian
    holidays_countries -- "uses" --> holidays_groups_christian
    holidays_groups_christian -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_islamic
    holidays_countries -- "uses" --> holidays_groups_islamic
    holidays_groups_islamic -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_chinese
    holidays_countries -- "uses" --> holidays_groups_chinese
    holidays_groups_chinese -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_hebrew
    holidays_countries -- "uses" --> holidays_groups_hebrew
    holidays_groups_hebrew -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_hindu
    holidays_countries -- "uses" --> holidays_groups_hindu
    holidays_groups_hindu -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_balinese_saka
    holidays_countries -- "uses" --> holidays_groups_balinese_saka
    holidays_groups_balinese_saka -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_buddhist
    holidays_countries -- "uses" --> holidays_groups_buddhist
    holidays_groups_buddhist -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_mandaean
    holidays_countries -- "uses" --> holidays_groups_mandaean
    holidays_groups_mandaean -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_mongolian
    holidays_countries -- "uses" --> holidays_groups_mongolian
    holidays_groups_mongolian -- "depends on" --> holidays_calendars
    holidays_holiday_base_HolidayBase -- "uses" --> holidays_groups_persian
    holidays_countries -- "uses" --> holidays_groups_persian
    holidays_groups_persian -- "depends on" --> holidays_calendars
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Common Holiday Groups subsystem is a collection of modules designed to define and group holidays based on shared religious or cultural calendars. This promotes reusability of holiday definitions across various country or regional modules within the holidays library.

### holidays.groups.christian
Encapsulates logic and definitions for Christian holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/christian.py" target="_blank" rel="noopener noreferrer">`holidays.groups.christian`</a>


### holidays.groups.islamic
Encapsulates logic and definitions for Islamic holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/islamic.py" target="_blank" rel="noopener noreferrer">`holidays.groups.islamic`</a>


### holidays.groups.chinese
Encapsulates logic and definitions for Chinese holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/chinese.py" target="_blank" rel="noopener noreferrer">`holidays.groups.chinese`</a>


### holidays.groups.hebrew
Encapsulates logic and definitions for Hebrew holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/hebrew.py" target="_blank" rel="noopener noreferrer">`holidays.groups.hebrew`</a>


### holidays.groups.hindu
Encapsulates logic and definitions for Hindu holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/hindu.py" target="_blank" rel="noopener noreferrer">`holidays.groups.hindu`</a>


### holidays.groups.balinese_saka
Encapsulates logic and definitions for Balinese Saka holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/balinese_saka.py" target="_blank" rel="noopener noreferrer">`holidays.groups.balinese_saka`</a>


### holidays.groups.buddhist
Encapsulates logic and definitions for Buddhist holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/buddhist.py" target="_blank" rel="noopener noreferrer">`holidays.groups.buddhist`</a>


### holidays.groups.mandaean
Encapsulates logic and definitions for Mandaean holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/mandaean.py" target="_blank" rel="noopener noreferrer">`holidays.groups.mandaean`</a>


### holidays.groups.mongolian
Encapsulates logic and definitions for Mongolian holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/mongolian.py" target="_blank" rel="noopener noreferrer">`holidays.groups.mongolian`</a>


### holidays.groups.persian
Encapsulates logic and definitions for Persian holidays, providing methods to add them to a collection for reusability.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/groups/persian.py" target="_blank" rel="noopener noreferrer">`holidays.groups.persian`</a>


### holidays.holiday_base.HolidayBase
Base class for holiday definitions.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/holiday_base.py#L57-L1296" target="_blank" rel="noopener noreferrer">`holidays.holiday_base.HolidayBase`:57-1296</a>


### holidays.countries
Module for country-specific holiday definitions.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/countries/__init__.py" target="_blank" rel="noopener noreferrer">`holidays.countries`</a>


### holidays.calendars
Module for calendar-related date calculations.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars" target="_blank" rel="noopener noreferrer">`holidays.calendars`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)