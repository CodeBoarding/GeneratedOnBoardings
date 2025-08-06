```mermaid
graph LR
    Driver_Context["Driver & Context"]
    ODPI_C_Interop_Layer["ODPI-C Interop Layer"]
    Connection_Management["Connection Management"]
    Statement_Execution["Statement Execution"]
    Row_Fetching["Row Fetching"]
    Data_Type_Marshalling["Data Type Marshalling"]
    LOB_Handling["LOB Handling"]
    Driver_Context -- "Initializes" --> ODPI_C_Interop_Layer
    Connection_Management -- "Uses" --> ODPI_C_Interop_Layer
    Connection_Management -- "Prepares" --> Statement_Execution
    Statement_Execution -- "Executes via" --> ODPI_C_Interop_Layer
    Statement_Execution -- "Binds params using" --> Data_Type_Marshalling
    Row_Fetching -- "Fetches via" --> ODPI_C_Interop_Layer
    Row_Fetching -- "Converts rows using" --> Data_Type_Marshalling
    LOB_Handling -- "Reads/Writes via" --> ODPI_C_Interop_Layer
    Row_Fetching -- "Delegates to" --> LOB_Handling
    click ODPI_C_Interop_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/godror/ODPI_C_Interop_Layer.md" "Details"
    click Connection_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/godror/Connection_Management.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Driver & Context
The entry point for the `database/sql` package. It's responsible for registering the `godror` driver and initializing the global ODPI-C context (`dpiContext`), which is required for all subsequent library calls.


**Related Classes/Methods**:

- `init()`
- `godrorDriver`
- `drv.Open()`


### ODPI-C Interop Layer [[Expand]](./ODPI_C_Interop_Layer.md)
A low-level facade that abstracts the ODPI-C library. It uses CGo to make direct calls to the C library, managing memory, handling C pointers, and translating error codes, effectively bridging the Go and C worlds.


**Related Classes/Methods**:

- `import "C"`
- `C.dpiContext_create`
- `C.dpiConn_create`
- `C.dpiStmt_execute`
- `C.dpiData`
- `C.dpiLob`


### Connection Management [[Expand]](./Connection_Management.md)
Represents a single database session and implements the `driver.Conn` interface. It encapsulates a C-level connection handle (`C.dpiConn`) and manages the session's lifecycle, including transactions (begin, commit, rollback) and statement preparation.


**Related Classes/Methods**:

- `conn`
- `(c *conn) PrepareContext()`
- `(c *conn) BeginTx()`
- `(c *conn) Commit()`
- `(c *conn) Rollback()`


### Statement Execution
Implements the `driver.Stmt` interface for a prepared SQL statement. It holds a C statement handle (`C.dpiStmt`), manages parameter binding (converting Go types to C), and executes the SQL against the database.


**Related Classes/Methods**:

- `stmt`
- `(s *stmt) ExecContext()`
- `(s *stmt) QueryContext()`
- `(s *stmt) Close()`


### Row Fetching
Implements the `driver.Rows` interface to iterate over a result set. Its primary role is to fetch data row-by-row from the C layer and manage the translation of ODPI-C data types into native Go types for application use.


**Related Classes/Methods**:

- `rows`
- `(r *rows) Columns()`
- `(r *rows) Next()`


### Data Type Marshalling
A specialized component responsible for the complex logic of converting data between Go types and ODPI-C's internal `dpiData` format. It is used during both parameter binding (Go to C) and row fetching (C to Go).


**Related Classes/Methods**:

- `(s *stmt) bind()`
- `(r *rows) Next()`
- `data.go`


### LOB Handling
Provides specialized handling for Large Object (LOB) types like `BLOB` and `CLOB`. It manages streaming reads and writes for data that is too large to fit in memory, interacting directly with the ODPI-C LOB APIs.


**Related Classes/Methods**:

- `Lob`
- `(r *Lob) Read()`
- `(w *Lob) Write()`
- `(l *Lob) Close()`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)