```mermaid
graph LR
    Core_Utilities_Foundation["Core Utilities & Foundation"]
    Data_Management["Data Management"]
    Core_Utilities_Foundation -- "processes data for" --> Data_Management
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

This architecture overview details the Core Utilities & Foundation component, which serves as the bedrock for the project by providing essential utility functions, architectural patterns, and reusable decorators. It interacts with the Data Management component, primarily by offering functionalities to process and manipulate dataset structures. The main flow involves various modules within Core Utilities & Foundation providing fundamental operations and design enforcement, which are then leveraged by other parts of the system, including data handling.

### Core Utilities & Foundation
This foundational component provides a comprehensive suite of general-purpose utility functions, core architectural elements, and reusable decorators. It includes functionalities for type checking, data manipulation (dictionaries, arrays/tensors), file system operations, and managing reproducibility. Furthermore, it defines fundamental classes and decorators for object-oriented programming, such as `final` for preventing subclassing and `abstract_group` for defining abstract method groups, contributing to the architectural structure and enforcing design patterns.


**Related Classes/Methods**:

- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L45-L57" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.isint` (45:57)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L437-L440" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.flatten` (437:440)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L417-L434" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.reshape` (417:434)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L38-L42" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.match` (38:42)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L60-L72" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.is_0d` (60:72)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L75-L83" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.dict_get` (75:83)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L86-L96" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._dict_get_out` (86:96)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L99-L100" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.dict_pop` (99:100)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L155-L171" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.any_get` (155:171)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L174-L186" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.any_pop` (174:186)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L259-L285" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.new_shape` (259:285)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L249-L256" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.expand_ellipsis` (249:256)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L353-L366" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.chunks.__init__` (353:366)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L371-L373" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.chunks.__iter__` (371:373)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L326-L338" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.ranges` (326:338)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L478-L504" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.concatenate` (478:504)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L507-L534" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.join` (507:534)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L537-L545" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._join_helper_args` (537:545)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L548-L556" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._join_helper_tuple` (548:556)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L559-L568" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._join_helper_numpy` (559:568)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L571-L576" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._join_helper_torch` (571:576)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L579-L582" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._join_helper_tumpy` (579:582)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L585-L590" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.is_iterable` (585:590)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L625-L629" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.axes_except` (625:629)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L632-L633" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.sum_except` (632:633)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L667-L678" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.convert_output_type` (667:678)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L681-L700" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._convert_output_class` (681:700)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L703-L709" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._convert_output_logit` (703:709)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L712-L718" target="_blank" rel="noopener noreferrer">`Alien.alien.utils._convert_output_prob` (712:718)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L652-L664" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.softmax` (652:664)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L731-L737" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.SelfDict.__init__` (731:737)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L739-L743" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.SelfDict.__setitem__` (739:743)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L751-L761" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.SelfDict.__getitem__` (751:761)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L763-L772" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.SelfDict.pop` (763:772)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/utils.py#L776-L794" target="_blank" rel="noopener noreferrer">`Alien.alien.utils.CachedDict.__init__` (776:794)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L57-L149" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.flatten_batch` (57:149)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L196-L248" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.normalize_args` (196:248)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L251-L253" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators._check_is_method` (251:253)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L256-L261" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators._get_arg_name` (256:261)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L264-L269" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators._get_batch_dim` (264:269)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L167-L173" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.do_normalize` (167:173)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L176-L192" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.sig_append` (176:192)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L272-L327" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.get_Xy` (272:327)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L330-L345" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators._get_xy_names` (330:345)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L374-L382" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.no_recursion` (374:382)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/decorators.py#L348-L370" target="_blank" rel="noopener noreferrer">`Alien.alien.decorators.RecursionContext` (348:370)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/classes.py#L15-L26" target="_blank" rel="noopener noreferrer">`Alien.alien.classes.final` (15:26)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/classes.py#L76-L97" target="_blank" rel="noopener noreferrer">`Alien.alien.classes.abstract_group` (76:97)</a>
- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/classes.py#L11-L12" target="_blank" rel="noopener noreferrer">`Alien.alien.classes.parent_locals` (11:12)</a>


### Data Management
This module is responsible for managing and interacting with datasets, particularly through the TeachableDataset class, which provides functionalities for creating, shuffling, and handling various data types.


**Related Classes/Methods**:

- <a href="https://github.com/Sanofi-Public/Alien/blob/master/alien/data/dataset.py#L15-L26" target="_blank" rel="noopener noreferrer">`Alien.alien.data.dataset.TeachableDataset.from_data` (15:26)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)