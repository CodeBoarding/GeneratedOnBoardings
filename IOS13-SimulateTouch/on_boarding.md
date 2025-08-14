```mermaid
graph LR
    Python_Client_Library["Python Client Library"]
    iOS_Daemon_Tweak["iOS Daemon/Tweak"]
    Configuration_Data_Persistence["Configuration & Data Persistence"]
    Scripting_Automation_Framework["Scripting/Automation Framework"]
    Scripting_Automation_Framework -- "uses" --> Python_Client_Library
    Python_Client_Library -- "communicates with" --> iOS_Daemon_Tweak
    iOS_Daemon_Tweak -- "interacts with" --> Python_Client_Library
    Python_Client_Library -- "interacts with" --> Configuration_Data_Persistence
    Configuration_Data_Persistence -- "interacts with" --> Python_Client_Library
    iOS_Daemon_Tweak -- "interacts with" --> Configuration_Data_Persistence
    Configuration_Data_Persistence -- "interacts with" --> iOS_Daemon_Tweak
    click Python_Client_Library href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/IOS13-SimulateTouch/Python_Client_Library.md" "Details"
    click iOS_Daemon_Tweak href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/IOS13-SimulateTouch/iOS_Daemon_Tweak.md" "Details"
    click Configuration_Data_Persistence href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/IOS13-SimulateTouch/Configuration_Data_Persistence.md" "Details"
    click Scripting_Automation_Framework href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/IOS13-SimulateTouch/Scripting_Automation_Framework.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The project's architecture is structured around a client-server model, enabling automated interaction with iOS devices. The Scripting/Automation Framework allows users to define and execute automated tasks using Python scripts. These scripts leverage the Python Client Library to communicate with the iOS Daemon/Tweak, which runs on the iOS device. The Python Client Library handles the serialization of commands and network communication, sending instructions to the iOS Daemon. The iOS Daemon/Tweak is responsible for receiving these commands, deserializing them, and injecting them as low-level touch and keyboard events into the iOS operating system. The Configuration & Data Persistence component manages the storage and retrieval of recorded touch sequences and application settings, supporting both on-device and off-device data management, which can be utilized by both the Python Client Library for recording/playback and the iOS Daemon for its operational data.

### Python Client Library [[Expand]](./Python_Client_Library.md)
Provides a high-level API for users and scripts to interact with the iOS Daemon. It handles command creation, serialization, network communication, and manages recording/playback of touch data.


**Related Classes/Methods**:

- <a href="https://github.com/xuan32546/IOS13-SimulateTouch/blob/master/layout/usr/lib/python3.7/site-packages/zxtouch/client.py" target="_blank" rel="noopener noreferrer">`zxtouch.client`</a>
- <a href="https://github.com/xuan32546/IOS13-SimulateTouch/blob/master/layout/usr/lib/python3.7/site-packages/zxtouch/datahandler.py" target="_blank" rel="noopener noreferrer">`zxtouch.datahandler`</a>


### iOS Daemon/Tweak [[Expand]](./iOS_Daemon_Tweak.md)
The on-device server component responsible for listening for commands, deserializing them, translating them into low-level iOS touch events, and injecting these events into the iOS operating system.


**Related Classes/Methods**:

- <a href="https://github.com/xuan32546/IOS13-SimulateTouch/blob/master/appdelegate/Tweak.xm" target="_blank" rel="noopener noreferrer">`Tweak.xm`</a>
- <a href="https://github.com/xuan32546/IOS13-SimulateTouch/blob/master/appdelegate/UIKeyboard.xm" target="_blank" rel="noopener noreferrer">`UIKeyboard.xm`</a>


### Configuration & Data Persistence [[Expand]](./Configuration_Data_Persistence.md)
Manages the storage and retrieval of recorded touch sequences, application settings, and other persistent data, supporting both on-device and off-device storage.


**Related Classes/Methods**: _None_

### Scripting/Automation Framework [[Expand]](./Scripting_Automation_Framework.md)
Represents the collection of user-defined Python scripts and their bundling mechanisms that leverage the Python Client Library to define and execute automated tasks on the iOS device.


**Related Classes/Methods**:

- <a href="https://github.com/xuan32546/IOS13-SimulateTouch/blob/master/Example-Scripts/Touch Simulation.bdl/simulate_touch.py" target="_blank" rel="noopener noreferrer">`simulate_touch.py`</a>
- <a href="https://github.com/xuan32546/IOS13-SimulateTouch/blob/master/Example-Scripts/Text Input and MORE.bdl/keyboard-test.py" target="_blank" rel="noopener noreferrer">`keyboard-test.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)