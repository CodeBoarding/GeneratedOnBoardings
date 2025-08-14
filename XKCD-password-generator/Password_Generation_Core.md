```mermaid
graph LR
    Password_Generation_Orchestrator["Password Generation Orchestrator"]
    Single_Password_Generator["Single Password Generator"]
    Word_Selector["Word Selector"]
    Acrostic_Applier["Acrostic Applier"]
    Casing_Strategy_Dispatcher["Casing Strategy Dispatcher"]
    Random_Casing_Transformer["Random Casing Transformer"]
    Word_Joiner["Word Joiner"]
    Delimiter_Chooser["Delimiter Chooser"]
    Password_Generation_Orchestrator -- "initiates generation by calling" --> Single_Password_Generator
    Single_Password_Generator -- "selects words using" --> Word_Selector
    Single_Password_Generator -- "applies acrostic rules using" --> Acrostic_Applier
    Single_Password_Generator -- "delegates casing transformation to" --> Casing_Strategy_Dispatcher
    Casing_Strategy_Dispatcher -- "applies random casing via" --> Random_Casing_Transformer
    Single_Password_Generator -- "joins words into password using" --> Word_Joiner
    Word_Joiner -- "selects delimiter via" --> Delimiter_Chooser
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Password Generation Core subsystem is responsible for the primary business logic of generating XKCD-style passwords. This includes the selection of words, integration of acrostics, application of various casing rules, and the final assembly of the password string.

### Password Generation Orchestrator
This component serves as the top-level public interface for initiating the generation of one or more XKCD-style passwords. It orchestrates the overall process by delegating the creation of individual passwords to the Single Password Generator.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:generate_xkcdpassword`</a>


### Single Password Generator
This is the core logic unit responsible for assembling a single password. It coordinates the sequence of operations: selecting words, applying acrostic rules, transforming word casing, and finally joining the words.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:gen_passwd`</a>


### Word Selector
Responsible for choosing the required number of words from a given wordlist, forming the foundational elements of the password.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:choose_words`</a>


### Acrostic Applier
This component applies acrostic constraints to the selected words. It ensures that the chosen words align with a specified initial letter pattern, if an acrostic is provided.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:find_acrostic`</a>


### Casing Strategy Dispatcher
Manages and dispatches various casing rules (e.g., random, alternating, first upper, lower, capitalize) to the chosen words based on configuration. It acts as a central point for applying different casing transformations.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:set_case`</a>
- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:alternating_case`</a>
- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:first_upper_case`</a>
- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:lower_case`</a>
- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:capitalize_case`</a>


### Random Casing Transformer
This component transforms words by randomly applying uppercase or lowercase to individual characters, introducing variability and enhancing password strength.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:random_case`</a>
- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:make_upper`</a>


### Word Joiner
Responsible for concatenating the processed words into the final password string. It can incorporate a randomly selected delimiter to further enhance password complexity.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:randomized_delimiter_join`</a>


### Delimiter Chooser
Selects a random delimiter from a predefined set of options. This delimiter is then used by the Word Joiner to separate words in the final password.


**Related Classes/Methods**:

- <a href="https://github.com/redacted/XKCD-password-generator/blob/master/xkcdpass/xkcd_password.py" target="_blank" rel="noopener noreferrer">`xkcdpass.xkcd_password:choose_delimiter`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)