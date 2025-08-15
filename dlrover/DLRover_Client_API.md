```mermaid
graph LR
    Job_Definition_API["Job Definition API"]
    Job_Submission_Orchestrator["Job Submission Orchestrator"]
    Platform_Specific_Job_Submitter["Platform-Specific Job Submitter"]
    Job_Definition_API -- "passes structured job configuration" --> Job_Submission_Orchestrator
    Job_Submission_Orchestrator -- "invokes" --> Platform_Specific_Job_Submitter
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The DLRover Client & API subsystem serves as the user-facing entry point for defining, configuring, and initiating distributed deep learning jobs within the DLRover ecosystem. It encapsulates the logic for job specification, initial processing, and delegating to platform-specific submission mechanisms.

### Job Definition API
This component provides the high-level, unified API for users to define distributed deep learning jobs. It acts as the primary user-facing interface, abstracting away the complexities of underlying platforms. Its responsibilities include parsing user-defined job specifications, performing initial validation, and transforming these specifications into structured internal configuration objects.


**Related Classes/Methods**:

- <a href="https://github.com/intelligent-machine-learning/dlrover/blob/master/dlrover/python/unified/api/base.py" target="_blank" rel="noopener noreferrer">`dlrover.python.unified.api.base`</a>


### Job Submission Orchestrator
This component acts as the central orchestrator for the job submission pipeline. It receives the structured job configuration from the Job Definition API, prepares the execution context, and dynamically identifies and invokes the appropriate platform-specific job submitter (e.g., for Ray, Kubernetes, etc.) based on the job's target environment. It manages the initial phase of job lifecycle before handing over to the platform-specific components.


**Related Classes/Methods**:

- <a href="https://github.com/intelligent-machine-learning/dlrover/blob/master/dlrover/python/unified/driver/main.py" target="_blank" rel="noopener noreferrer">`dlrover.python.unified.driver.main`</a>


### Platform-Specific Job Submitter
This component represents a concrete implementation of a platform-specific job submitter. Its responsibility is to manage the submission and initial monitoring of DLRover jobs on a particular distributed computing platform (e.g., Ray). It encapsulates platform-specific configurations, translates DLRover's internal job representation into platform-native commands, and interacts directly with the platform's job management APIs.


**Related Classes/Methods**:

- <a href="https://github.com/intelligent-machine-learning/dlrover/blob/master/dlrover/client/platform/ray/ray_job_submitter.py" target="_blank" rel="noopener noreferrer">`dlrover.client.platform.ray.ray_job_submitter`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)