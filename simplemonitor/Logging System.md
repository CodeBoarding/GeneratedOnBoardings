## Logging System Overview

The Logging System in SimpleMonitor is responsible for recording monitor results and application events to various destinations. It provides a consistent interface for recording and storing information about the system's operation. The core components involved are `SimpleMonitor`, `Logger`, `FileLogger`, `DBLogger`, `SeqLogger`, `MQTTLogger`, `NetworkLogger`, `Listener`, and `util`.

Here's a high-level data flow diagram illustrating the interaction between these components:

```mermaid
graph LR
    A[SimpleMonitor] -- Loads/Manages --> B(Logger) 
    B -- Defines Interface --> C(FileLogger) 
    B -- Defines Interface --> D(DBLogger) 
    B -- Defines Interface --> E(SeqLogger) 
    B -- Defines Interface --> F(MQTTLogger) 
    B -- Defines Interface --> G(NetworkLogger) 
    G -- Listens --> H(Listener)
    A -- Uses --> I(util)
    A -- Calls --> B
    A -- Calls --> C
    A -- Calls --> D
    A -- Calls --> E
    A -- Calls --> F
    A -- Calls --> G
```


**Component: SimpleMonitor**
*   **Description**: Orchestrates the monitoring process, managing loggers and coordinating result logging.
*   **Functionality**: Loads loggers, logs results, and manages the overall monitoring workflow.
*   **Interaction**: It loads and manages `Logger` instances, calls their methods to save results, and uses `util` for configuration and data formatting.
*   **Source Files**: `repos.simplemonitor.simplemonitor.simplemonitor.SimpleMonitor`

**Component: Logger**
*   **Description**: Provides a base class for loggers, defining common functionality and the interface for saving results.
*   **Functionality**: Manages logger configuration, batch processing, and dependency checking.
*   **Interaction**: It's extended by specific logger implementations like `FileLogger`, `DBLogger`, `SeqLogger`, `MQTTLogger`, and `NetworkLogger`. It receives calls from `SimpleMonitor` to save results.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.logger.Logger`

**Component: FileLogger**
*   **Description**: Handles logging to files in various formats.
*   **Functionality**: Extends `Logger` and provides methods for saving results to a file.
*   **Interaction**: It's a subclass of `Logger` and is called by `SimpleMonitor` to save results to files.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.file.FileLogger`, `repos.simplemonitor.simplemonitor.Loggers.file.FileLoggerNG`, `repos.simplemonitor.simplemonitor.Loggers.file.HTMLLogger`, `repos.simplemonitor.simplemonitor.Loggers.file.JsonLogger`

**Component: DBLogger**
*   **Description**: Handles logging to a database.
*   **Functionality**: Extends `Logger` and provides methods for checking and rolling forward the database schema.
*   **Interaction**: It's a subclass of `Logger` and is called by `SimpleMonitor` to save results to a database.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.db.DBLogger`, `repos.simplemonitor.simplemonitor.Loggers.db.DBFullLogger`, `repos.simplemonitor.simplemonitor.Loggers.db.DBStatusLogger`

**Component: SeqLogger**
*   **Description**: Sends logs to a Seq server.
*   **Functionality**: Extends `Logger` and provides a method for sending logs to the Seq server.
*   **Interaction**: It's a subclass of `Logger` and is called by `SimpleMonitor` to send logs to a Seq server.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.seq.SeqLogger`

**Component: MQTTLogger**
*   **Description**: Sends logs via MQTT.
*   **Functionality**: Extends `Logger`.
*   **Interaction**: It's a subclass of `Logger` and is called by `SimpleMonitor` to send logs via MQTT.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.mqtt.MQTTLogger`

**Component: NetworkLogger**
*   **Description**: Sends logs over the network.
*   **Functionality**: Extends `Logger` and provides a method for processing batched data.
*   **Interaction**: It's a subclass of `Logger` and is called by `SimpleMonitor` to send logs over the network. It sends data to the `Listener`.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.network.NetworkLogger`

**Component: Listener**
*   **Description**: Listens for network log messages.
*   **Functionality**: Handles incoming data and processes it.
*   **Interaction**: It receives data from `NetworkLogger`.
*   **Source Files**: `repos.simplemonitor.simplemonitor.Loggers.network.Listener`

**Component: util**
*   **Description**: Provides utility functions for configuration and data formatting.
*   **Functionality**: Offers functions for getting configuration options, formatting datetimes, and encoding/decoding JSON data.
*   **Interaction**: It's used by `SimpleMonitor` and `Logger` for configuration and data formatting tasks.
*   **Source Files**: `repos.simplemonitor.simplemonitor.util`
