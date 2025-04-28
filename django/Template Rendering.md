## Template Rendering Overview

This diagram illustrates the flow of template rendering in Django, starting from a request and ending with an HTTP response containing the rendered content.

```mermaid
graph LR
    A[Request] --> B(Rendering Shortcut: render) -- calls --> C(Template Loader) 
    C --> D(Template Engine) -- uses --> E(Template) 
    D --> F(Context) -- provides data to --> E
    E -- renders with --> F -- populates --> G(Rendered Template) 
    G --> H(HTTP Response) -- sends --> I[Client]
    D --> J(Template Response) -- returns --> H


```

## Components

Here's a breakdown of each component in the diagram:
