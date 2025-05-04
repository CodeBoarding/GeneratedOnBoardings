# Textual: High-Level Data Flow Overview

Textual is a Rapid Application Development (RAD) framework for creating sophisticated text-based user interfaces (TUIs) in Python. It leverages modern web development concepts like CSS and reactive programming to provide a declarative and efficient way to build interactive terminal applications.

```mermaid
flowchart LR
    A[App Driver] -- Initializes & Manages --> B(DOM)
    B -- Queries & Updates --> C[
Component Styling
(CSS)
]
    A -- Sends Events --> D[Event System]
    D -- Dispatches --> A
    A -- Triggers --> E[Action Dispatcher]
    E -- Modifies State --> F[Reactive System]
    F -- Notifies --> B
    A -- Applies --> G[Theming]
    G -- Affects Style --> C
    B -- Calculates Layout --> H[Layout Management]
    H -- Positions Widgets --> A

click A href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//App Driver.md"
click B href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//DOM.md"
click C href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//Component Styling (CSS).md"
click D href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//Event System.md"
click E href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//Action Dispatcher.md"
click F href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//Application Core.md"
click G href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//Application Core.md"
click H href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/textual//Layout Engine.md"

```

## Component Descriptions

**App Driver:** The App Driver is the entry point and central controller of the Textual application. It initializes the terminal, manages the application lifecycle, and orchestrates the interaction between different components. It receives events from the Event System and dispatches actions, while also using the Layout Management to position widgets on the screen. It also applies Theming to the application.

**DOM (Document Object Model):** The DOM represents the UI as a tree structure, reflecting the hierarchy of widgets. It allows for querying and manipulation of widgets and their properties. The DOM is initialized and managed by the App Driver. It is styled by the Component Styling (CSS) and its layout is calculated by the Layout Management. The Reactive System notifies the DOM of state changes, triggering UI updates.

**Component Styling (CSS):** The CSS Engine handles the styling and layout of UI components using CSS-like syntax. It parses stylesheets and applies styles to widgets in the DOM. The Theming component affects the style of the application through the CSS engine.

**Event System:** The Event System manages the flow of events within the application, including keyboard input, mouse actions, and custom events. It dispatches events to the appropriate widgets, which are managed by the App Driver.

**Action Dispatcher:** The Action Dispatcher handles actions triggered by user input or other events. It maps actions to methods on widgets and executes those methods. It modifies the state of the application, which is reflected in the Reactive System.

**Reactive System:** The Reactive System handles reactive variables and their updates. It automatically updates the UI when reactive variables change, ensuring that the UI reflects the current state of the application. It notifies the DOM of state changes.

**Theming:** Theming handles the application's theme and styling. It allows users to customize the appearance of the application by changing the theme. It affects the style of the application through the CSS engine.

**Layout Management:** The Layout Management arranges widgets on the screen using different layout strategies such as docking, grids, and static positioning. It calculates the positions and sizes of widgets based on layout constraints. It positions widgets on the screen, which is managed by the App Driver.