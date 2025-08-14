```mermaid
graph LR
    Documentation_Platform["Documentation Platform"]
    Core_UI_Components["Core UI Components"]
    Theming_and_Customization_Engine["Theming and Customization Engine"]
    Design_Language_System_Assets["Design Language/System Assets"]
    Internationalization_i18n_Module["Internationalization (i18n) Module"]
    Documentation_Platform -- "leverages for dynamic theme application" --> Theming_and_Customization_Engine
    Documentation_Platform -- "consumes and presents" --> Core_UI_Components
    Documentation_Platform -- "uses to display design system specifications" --> Design_Language_System_Assets
    Documentation_Platform -- "consumes and presents for localized content" --> Internationalization_i18n_Module
    Theming_and_Customization_Engine -- "interacts with and applies design tokens from" --> Design_Language_System_Assets
    Design_Language_System_Assets -- "governs the appearance and behavior of" --> Core_UI_Components
    Internationalization_i18n_Module -- "provides locale-specific content to" --> Core_UI_Components
    click Documentation_Platform href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/ant-design/Documentation_Platform.md" "Details"
    click Core_UI_Components href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/ant-design/Core_UI_Components.md" "Details"
    click Theming_and_Customization_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/ant-design/Theming_and_Customization_Engine.md" "Details"
    click Internationalization_i18n_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/ant-design/Internationalization_i18n_Module.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Ant Design architecture is built around a central `Documentation Platform` that serves as the user-facing gateway to the entire design system. This platform dynamically integrates `Core UI Components`, allowing users to explore and interact with them. The visual presentation of both the documentation and the components is highly customizable through the `Theming and Customization Engine`, which applies design tokens defined within the `Design Language/System Assets`. To ensure global accessibility, the `Internationalization (i18n) Module` provides multi-language support across the platform and its components. This modular and interconnected design allows for a flexible, maintainable, and highly customizable UI component library.

### Documentation Platform [[Expand]](./Documentation_Platform.md)
The primary interface for showcasing, documenting, and interacting with UI components and the design system.


**Related Classes/Methods**:

- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/pages/" target="_blank" rel="noopener noreferrer">`content within .dumi/pages/`</a>
- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/theme/" target="_blank" rel="noopener noreferrer">`content within .dumi/theme/`</a>
- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/hooks/" target="_blank" rel="noopener noreferrer">`content within .dumi/hooks/`</a>


### Core UI Components [[Expand]](./Core_UI_Components.md)
The actual reusable UI components (e.g., buttons, inputs, cards) that form the building blocks for applications.


**Related Classes/Methods**:

- <a href="https://github.com/ant-design/ant-design/blob/master/components/" target="_blank" rel="noopener noreferrer">`content within components/`</a>


### Theming and Customization Engine [[Expand]](./Theming_and_Customization_Engine.md)
Manages visual themes and enables dynamic customization of design tokens.


**Related Classes/Methods**:

- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/pages/index/components/Theme/" target="_blank" rel="noopener noreferrer">`content within .dumi/pages/index/components/Theme/`</a>
- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/theme/SiteThemeProvider.tsx" target="_blank" rel="noopener noreferrer">`SiteThemeProvider.tsx`</a>


### Design Language/System Assets
Encapsulates foundational visual design guidelines, design tokens, and standardized styles.


**Related Classes/Methods**:

- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/theme/builtins/ColorPaletteTool/" target="_blank" rel="noopener noreferrer">`content within .dumi/theme/builtins/ColorPaletteTool/`</a>
- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/theme/builtins/ColorPalettes/" target="_blank" rel="noopener noreferrer">`content within .dumi/theme/builtins/ColorPalettes/`</a>


### Internationalization (i18n) Module [[Expand]](./Internationalization_i18n_Module.md)
Provides multi-language support for the documentation site and components.


**Related Classes/Methods**:

- <a href="https://github.com/ant-design/ant-design/blob/master/.dumi/hooks/useLocale.ts" target="_blank" rel="noopener noreferrer">`useLocale.ts`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)