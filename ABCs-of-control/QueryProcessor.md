```mermaid
graph LR
    ABCsOfControlPlugin["ABCsOfControlPlugin"]
    User_Interaction_Handler["User Interaction Handler"]
    Note_Content_Manager["Note Content Manager"]
    Highlight_Quote_Formatter["Highlight/Quote Formatter"]
    Unclassified["Unclassified"]
    User_Interaction_Handler -- "provides input to" --> ABCsOfControlPlugin
    ABCsOfControlPlugin -- "orchestrates" --> User_Interaction_Handler
    ABCsOfControlPlugin -- "delegates formatting to" --> Highlight_Quote_Formatter
    Highlight_Quote_Formatter -- "returns formatted content to" --> ABCsOfControlPlugin
    ABCsOfControlPlugin -- "delegates note modification to" --> Note_Content_Manager
    Note_Content_Manager -- "modifies notes for" --> ABCsOfControlPlugin
    ABCsOfControlPlugin -- "sends feedback to" --> User_Interaction_Handler
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The "ABCs of Control" plugin for Obsidian is centered around the `ABCsOfControlPlugin` class, which serves as the primary orchestrator for all plugin functionalities. User interactions, such as highlighting text or adding quotes, are managed by the `User Interaction Handler`, which captures events and gathers necessary input. The `ABCsOfControlPlugin` then coordinates with the `Highlight/Quote Formatter` to structure the user's input into the appropriate Markdown format. Finally, the `Note Content Manager` is responsible for seamlessly integrating these formatted highlights and quotes into the user's Obsidian notes, ensuring proper placement and persistence. This architecture emphasizes a clear separation of concerns, with the main plugin class directing the flow and specialized components handling specific tasks like UI, content formatting, and note manipulation.

### ABCsOfControlPlugin
The core plugin class, orchestrating all functionalities, managing settings, and coordinating interactions between other components.


**Related Classes/Methods**:

- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts#L35-L425" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin`:35-425</a>


### User Interaction Handler
Manages user input events (ribbon icon clicks, commands, editor context menu interactions) and handles displaying user feedback and input modals.


**Related Classes/Methods**:

- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.onload`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.addRibbonIcon`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.addCommand`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.registerEvent`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.openColorPicker`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.openPromptModal`</a>


### Note Content Manager
Handles reading, modifying, and writing content to Obsidian notes, specifically for adding highlights and quotes to designated sections.


**Related Classes/Methods**:

- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.addHighlightToNote`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.handleQuote`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.getFileFromView`</a>


### Highlight/Quote Formatter
Responsible for formatting selected text and comments into the appropriate Markdown syntax for highlights and quotes, including language-specific section headers.


**Related Classes/Methods**:

- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.formatHighlight`</a>
- <a href="https://github.com/waheed11/ABCs-of-control/blob/mainsrc/main.ts" target="_blank" rel="noopener noreferrer">`ABCsOfControlPlugin.detectArabicContent`</a>


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)