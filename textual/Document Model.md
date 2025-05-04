```mermaid
graph LR
    DocumentBase -- Inherited by --> Document
    DocumentBase -- Inherited by --> SyntaxAwareDocument
    Document -- Uses --> EditHistory
    Document -- Creates --> EditResult
    Document -- Used by --> WrappedDocument
    Document -- Used by --> DocumentNavigator
    TextArea -- Manages --> Document
    TextArea -- Applies theme from --> TextAreaTheme
    TextArea -- Uses --> WrappedDocument



```