```mermaid
graph LR
    Gregorian_Calendar_Utilities["Gregorian Calendar Utilities"]
    Specialized_Calendar_Implementations["Specialized Calendar Implementations"]
    Specialized_Calendar_Implementations -- "leverages utilities from" --> Gregorian_Calendar_Utilities
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `holidays` project is structured around two core architectural components: `Gregorian Calendar Utilities` and `Specialized Calendar Implementations`. The `Gregorian Calendar Utilities` component serves as a foundational layer, providing essential date calculation functionalities based on the Gregorian calendar. This includes common operations like determining Nth weekdays and calculating time differences. Building upon this foundation, the `Specialized Calendar Implementations` component comprises a suite of modules, each dedicated to accurately calculating holidays within various non-Gregorian calendar systems. These specialized modules leverage the utilities provided by the `Gregorian Calendar Utilities` for conversions and interactions with Gregorian dates, ensuring accurate holiday determination across diverse cultural and religious contexts. This clear separation of concerns allows for modularity and extensibility, enabling the addition of new calendar systems without impacting existing implementations.

### Gregorian Calendar Utilities
This component provides fundamental, reusable utilities for Gregorian calendar date calculations. Its functionalities include determining Nth weekdays, calculating time differences, and identifying specific dates (e.g., all Sundays). It acts as a foundational layer, offering core date manipulation capabilities that other calendar systems may utilize for conversions or interactions with Gregorian dates.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/gregorian.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.gregorian`:1-9999</a>


### Specialized Calendar Implementations
This component represents a collection of distinct modules, each solely responsible for implementing the algorithms and logic required to calculate specific holidays or significant dates within its respective non-Gregorian calendar system. This includes handling unique calendar rules, leap years, and historical variations specific to calendars such as Balinese Saka, Buddhist, Chinese, Hebrew, Hindu, Islamic, Mandaean, Mongolian, Persian, Sinhala, Thai, and Tibetan. These modules are crucial for accurate holiday date determination across diverse cultural and religious contexts.


**Related Classes/Methods**:

- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/balinese_saka.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.balinese_saka`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/buddhist.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.buddhist`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/chinese.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.chinese`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/hebrew.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.hebrew`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/hindu.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.hindu`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/islamic.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.islamic`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/mandaean.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.mandaean`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/mongolian.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.mongolian`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/persian.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.persian`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/sinhala.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.sinhala`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/thai.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.thai`:1-9999</a>
- <a href="https://github.com/vacanza/holidays/blob/dev/holidays/calendars/tibetan.py#L1-L9999" target="_blank" rel="noopener noreferrer">`holidays.calendars.tibetan`:1-9999</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)