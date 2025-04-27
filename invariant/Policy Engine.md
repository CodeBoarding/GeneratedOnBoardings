```mermaid
graph LR
    A[Input Processing] -- provides input data --> B(Policy Loading and Parsing)
    B -- creates AST --> C(Language Linking and Typing)
    C -- links and types --> D(Runtime Rule Application)
    D -- applies rules using --> E(Runtime Evaluation)
    E -- evaluates expressions --> D
    D -- collects errors --> F(Error Handling)
    B -- handles errors --> F
    C -- handles errors --> F
    E -- handles errors --> F
    subgraph Policy Engine
        B
        C
        D
        E
    end
    G(Monitor) --"loads policies into"--> B
    G -- analyzes input using --> Policy Engine
    Policy Engine -- reports --> F
    H(LocalPolicy) -- represents --> B
    I(RemotePolicy) -- represents --> B




```

**Component: Input Processing**
*Description*: Processes and prepares the input data for analysis. It encapsulates the input data in an `Input` object, providing methods for accessing and manipulating the data during runtime. It provides the input data to the `Policy Loading and Parsing` component.
*Relevant source files*: `invariant.analyzer.runtime.input.Input`

**Component: Policy Loading and Parsing**
*Description*: Loads and parses policy files or strings into an abstract syntax tree (AST) representation. It uses the parser module to convert the policy language into a structured format suitable for analysis. It receives input from `Input Processing` and creates an AST for `Language Linking and Typing`.
*Relevant source files*: `invariant.analyzer.language.parser.parse`, `invariant.analyzer.language.parser.parse_file`, `repos.invariant.invariant.analyzer.policy.LocalPolicy.from_file`, `repos.invariant.invariant.analyzer.policy.LocalPolicy.from_string`

**Component: Language Linking and Typing**
*Description*: Links and performs type checking on the policy language elements. It ensures that the policy language is well-formed and that all variables and functions are properly defined and typed. It receives the AST from `Policy Loading and Parsing` and passes the linked and typed representation to `Runtime Rule Application`.
*Relevant source files*: `invariant.analyzer.language.linking.link`, `invariant.analyzer.language.typing.typing`

**Component: Runtime Rule Application**
*Description*: Applies the rules defined in the policy to the input data during runtime. It iterates through the rules in a RuleSet and applies each rule to the input, collecting any errors that occur. It receives the linked and typed policy from `Language Linking and Typing` and uses `Runtime Evaluation` to evaluate the rules.
*Relevant source files*: `invariant.analyzer.runtime.rule.RuleSet.apply`, `invariant.analyzer.runtime.rule.Rule.apply`

**Component: Runtime Evaluation**
*Description*: Evaluates expressions and conditions within the policy rules during runtime. It uses an Interpreter to traverse the AST and evaluate expressions based on the current variable store and global variables. It is used by `Runtime Rule Application` to evaluate the conditions and actions of the rules.
*Relevant source files*: `repos.invariant.invariant.analyzer.runtime.evaluation.Interpreter.eval`, `repos.invariant.invariant.analyzer.runtime.evaluation.Interpreter.assignments`

**Component: Error Handling**
*Description*: Handles errors that occur during policy loading, analysis, or runtime execution. It defines custom error types and provides mechanisms for reporting and handling errors. It receives errors from all components of the Policy Engine and the Monitor.
*Relevant source files*: `invariant.analyzer.stdlib.invariant.errors.PolicyLoadingError`, `invariant.analyzer.stdlib.invariant.errors.AnalysisResult`, `invariant.analyzer.stdlib.invariant.errors.UnhandledError`, `repos.invariant.invariant.analyzer.remote_policy.handle_error_response`

**Component: Monitor**
*Description*: Monitors the system and runs analysis based on loaded policies. It provides a high-level interface for loading policies, analyzing input data, and handling errors. It loads policies into `Policy Loading and Parsing` and analyzes input using the `Policy Engine`.
*Relevant source files*: `repos.invariant.invariant.analyzer.monitor.Monitor`, `repos.invariant.invariant.analyzer.monitor.Monitor.run`

**Component: LocalPolicy**
*Description*: Represents a policy loaded from a local file or string. It handles the parsing and analysis of the policy, and provides methods for applying the policy to input data. It represents the policies loaded into `Policy Loading and Parsing`.
*Relevant source files*: `repos.invariant.invariant.analyzer.policy.LocalPolicy`

**Component: RemotePolicy**
*Description*: Represents a policy loaded from a remote service. It handles the communication with the remote service and the analysis of the policy. It represents the policies loaded into `Policy Loading and Parsing`.
*Relevant source files*: `repos.invariant.invariant.analyzer.remote_policy.RemotePolicy`
