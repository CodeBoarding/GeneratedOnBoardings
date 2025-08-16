```mermaid
graph LR
    Kubernetes_Control_Plane_API_Server_etcd_["Kubernetes Control Plane (API Server & etcd)"]
    Custom_Resource_Definitions_CRDs_["Custom Resource Definitions (CRDs)"]
    Core_Cluster_API_Controllers["Core Cluster API Controllers"]
    Infrastructure_Providers["Infrastructure Providers"]
    Bootstrap_Providers["Bootstrap Providers"]
    Control_Plane_Providers["Control Plane Providers"]
    Webhooks["Webhooks"]
    clusterctl_CLI_Tool["clusterctl CLI Tool"]
    clusterctl_CLI_Tool -- "creates/updates" --> Custom_Resource_Definitions_CRDs_
    clusterctl_CLI_Tool -- "interacts with" --> Kubernetes_Control_Plane_API_Server_etcd_
    Kubernetes_Control_Plane_API_Server_etcd_ -- "invokes" --> Webhooks
    Webhooks -- "validates/mutates" --> Custom_Resource_Definitions_CRDs_
    Core_Cluster_API_Controllers -- "reconciles" --> Custom_Resource_Definitions_CRDs_
    Core_Cluster_API_Controllers -- "delegates to" --> Infrastructure_Providers
    Core_Cluster_API_Controllers -- "delegates to" --> Bootstrap_Providers
    Core_Cluster_API_Controllers -- "delegates to" --> Control_Plane_Providers
    Infrastructure_Providers -- "interacts with" --> Kubernetes_Control_Plane_API_Server_etcd_
    Bootstrap_Providers -- "interacts with" --> Kubernetes_Control_Plane_API_Server_etcd_
    Control_Plane_Providers -- "interacts with" --> Kubernetes_Control_Plane_API_Server_etcd_
    click Kubernetes_Control_Plane_API_Server_etcd_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cluster-api/Kubernetes_Control_Plane_API_Server_etcd_.md" "Details"
    click Core_Cluster_API_Controllers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cluster-api/Core_Cluster_API_Controllers.md" "Details"
    click Webhooks href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cluster-api/Webhooks.md" "Details"
    click clusterctl_CLI_Tool href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cluster-api/clusterctl_CLI_Tool.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Cluster API project extends Kubernetes to manage the lifecycle of Kubernetes clusters themselves. It operates by introducing Custom Resource Definitions (CRDs) that define the desired state of clusters, machines, and their associated infrastructure. Core Cluster API Controllers continuously reconcile these CRDs, delegating specific provisioning and configuration tasks to various pluggable providers (Infrastructure, Bootstrap, and Control Plane Providers). All interactions and state changes are managed through the Kubernetes API Server, with Webhooks ensuring data integrity and policy enforcement for Cluster API resources. The `clusterctl` CLI tool serves as the primary user interface for orchestrating these cluster lifecycle operations.

### Kubernetes Control Plane (API Server & etcd) [[Expand]](./Kubernetes_Control_Plane_API_Server_etcd_.md)
Acts as the central hub for all API interactions and the persistent store for all cluster data, including Cluster API Custom Resources.


**Related Classes/Methods**: _None_

### Custom Resource Definitions (CRDs)
Define the declarative API for managing Kubernetes clusters, extending the Kubernetes API with Cluster API-specific resources like `Cluster`, `Machine`, `MachineDeployment`.


**Related Classes/Methods**: _None_

### Core Cluster API Controllers [[Expand]](./Core_Cluster_API_Controllers.md)
Watches for changes to Cluster API CRs and reconciles the desired state with the actual state, orchestrating cluster creation, update, and deletion.


**Related Classes/Methods**: _None_

### Infrastructure Providers
Provisions and manages the underlying infrastructure (e.g., VMs, networks) for a Kubernetes cluster on a specific cloud or platform.


**Related Classes/Methods**: _None_

### Bootstrap Providers
Installs and configures Kubernetes components (e.g., `kubeadm`) on newly provisioned machines to turn them into Kubernetes nodes.


**Related Classes/Methods**: _None_

### Control Plane Providers
Manages the lifecycle of Kubernetes control plane components (e.g., `kube-apiserver`) on the provisioned infrastructure.


**Related Classes/Methods**: _None_

### Webhooks [[Expand]](./Webhooks.md)
Intercepts API requests for Cluster API CRs to enforce policies, validate data, and set default values.


**Related Classes/Methods**: _None_

### clusterctl CLI Tool [[Expand]](./clusterctl_CLI_Tool.md)
Provides a command-line interface for users to interact with Cluster API, facilitating setup, cluster creation, upgrade, and deletion.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)