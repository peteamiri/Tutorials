This is an extensive list of DevOps concepts and terminology, categorized by their primary function within the software delivery lifecycle.

### **1. Core Methodologies & Culture**
These terms define the philosophy and human element of DevOps.

*   **DevOps:** A cultural and professional movement that stresses communication, collaboration, and integration between software developers and IT operations professionals to automate and speed up software delivery.
*   **Agile:** An iterative approach to project management and software development that helps teams deliver value to their customers faster and with fewer headaches.
*   **Silos:** Isolated teams or departments that do not share information or processes with others. DevOps aims to "break down silos."
*   **Shift Left:** The practice of moving testing, security, and validation tasks earlier in the development process (to the "left" on a timeline) to catch issues sooner.
*   **Blameless Post-Mortem:** A meeting held after an incident to analyze what went wrong without assigning blame to individuals, focusing instead on process and systemic improvements.
*   **CALMS:** A conceptual framework for DevOps adoption: **C**ulture, **A**utomation, **L**ean, **M**easurement, and **S**haring.
*   **ChatOps:** The use of chat clients (like Slack or Microsoft Teams) to manage technical and business operations, often via bots that execute commands.
*   **Psychological Safety:** A cultural condition where team members feel safe to take risks and be vulnerable (e.g., admitting a mistake) without fear of negative consequences.
*   **Value Stream Mapping (VSM):** A lean-management method for analyzing the current state and designing a future state for the series of events that take a product or service from its beginning through to the customer.

### **2. Software Development Lifecycle (SDLC)**
Terms related to how code is written, integrated, and deployed.

*   **CI/CD:**
    *   **Continuous Integration (CI):** The practice of automating the integration of code changes from multiple contributors into a single software project. (Key goal: Prevent "merge hell").
    *   **Continuous Delivery (CD):** An extension of CI where code changes are automatically prepared for a release to production. Human approval may still be required.
    *   **Continuous Deployment:** The next step after Continuous Delivery, where every change that passes all stages of your production pipeline is released to your customers automatically, with no human intervention.
*   **Pipeline:** A set of automated processes (build, test, deploy) that allow developers and DevOps professionals to reliably and efficiently compile, build, and deploy code to their production compute platforms.
*   **Artifact:** Any file produced by a build process, such as a compiled binary, a library, or a Docker image.
*   **Version Control System (VCS):** Tools (like Git) that track changes to source code over time.
*   **Trunk-Based Development:** A source-control branching model where developers collaborate on code in a single branch called "trunk" (or main/master), resisting long-lived feature branches.
*   **Technical Debt:** The implied cost of additional rework caused by choosing an easy (limited) solution now instead of using a better approach that would take longer.

### **3. Infrastructure & Operations**
Terms describing how environments are built, managed, and maintained.

*   **Infrastructure as Code (IaC):** Managing and provisioning computer data centers through machine-readable definition files, rather than physical hardware configuration or interactive configuration tools.
*   **Idempotency:** A property of operations where the result is the same whether you run it once or multiple times. Crucial for IaC (e.g., running a script to "install Nginx" should work fine even if Nginx is already installed).
*   **Immutable Infrastructure:** An approach where servers are never modified after they're deployed. If something needs to be updated, you replace the entire server/container with a new one.
*   **Configuration Management:** Systems engineering process for establishing and maintaining consistency of a product's performance, functional, and physical attributes with its requirements, design, and operational information.
*   **Snowflake Server:** A server that has been manually configured and tweaked so much over time that it is unique and difficult to reproduce. (DevOps discourages this).
*   **Provisioning:** The process of setting up IT infrastructure. It can also refer to the steps required to manage access to data and resources, and make them available to users and systems.
*   **Serverless:** A cloud-native development model that allows developers to build and run applications without having to manage servers.

### **4. Containers & Orchestration**
Modern virtualization technology central to most DevOps workflows.

*   **Containerization:** Packaging software code with just the operating system (OS) libraries and dependencies required to run the code to create a single lightweight executable—called a container (e.g., Docker).
*   **Orchestration:** The automated configuration, coordination, and management of computer systems and software. (e.g., Kubernetes is a container orchestration tool).
*   **Microservices:** An architectural style that structures an application as a collection of loosely coupled services, which implement business capabilities.
*   **Service Mesh:** A dedicated infrastructure layer for facilitating service-to-service communications between microservices, often handling things like load balancing and encryption.
*   **Pod:** The smallest deployable unit of computing that can be created and managed in Kubernetes.

### **5. Deployment Strategies**
Techniques for releasing software to users with minimal downtime and risk.

*   **Blue-Green Deployment:** A technique that reduces downtime and risk by running two identical production environments called Blue and Green. Only one of the environments is live at any time.
*   **Canary Release:** Rolling out software to a small subset of users (like a canary in a coal mine) to test it before rolling it out to the entire user base.
*   **Rolling Deployment:** Updating instances of an application incrementally (e.g., 2 at a time) rather than all at once.
*   **Dark Launching:** Releasing features to production but keeping them hidden from users (often using feature flags) to test performance in the real world.
*   **Feature Flags (Toggles):** A coding technique that allows you to turn specific features on or off during runtime without deploying new code.

### **6. Observability & Metrics**
How to measure success and health.

*   **Observability:** A measure of how well internal states of a system can be inferred from knowledge of its external outputs. It usually consists of **Logs, Metrics, and Traces**.
*   **Telemetry:** The automatic recording and transmission of data from remote or inaccessible sources to an IT system in a different location for monitoring and analysis.
*   **SLA (Service Level Agreement):** A contract between a service provider and a customer that specifies what services will be provided and the level of service expected.
*   **SLO (Service Level Objective):** A specific measurable characteristic of the SLA such as availability, throughput, frequency, response time, or quality.
*   **SLI (Service Level Indicator):** The actual metric used to measure the performance of a service (e.g., error rate, latency) to see if you are meeting the SLO.
*   **MTTR (Mean Time To Recovery/Restore):** The average time it takes to recover from a product or system failure.
*   **MTBF (Mean Time Between Failures):** The predicted elapsed time between inherent failures of a mechanical or electronic system during normal system operation.
*   **DORA Metrics:** Four key metrics used to measure DevOps performance (Deployment Frequency, Lead Time for Changes, Change Failure Rate, Time to Restore Service).

### **7. Security (DevSecOps)**
Integrating security into the DevOps pipeline.

*   **DevSecOps:** The philosophy of integrating security practices within the DevOps process.
*   **SAST (Static Application Security Testing):** Testing the source code, byte code, or binary code of an application for security vulnerabilities (White-box testing).
*   **DAST (Dynamic Application Security Testing):** Testing an application in its running state to find security vulnerabilities (Black-box testing).
*   **Secrets Management:** The tools and methods used to manage digital authentication credentials (secrets), including passwords, keys, APIs, and tokens.
*   **Supply Chain Security:** Ensuring that all components of software (libraries, dependencies, base images) are secure and have not been tampered with.

### **8. Reliability Engineering**
*   **SRE (Site Reliability Engineering):** A discipline that incorporates aspects of software engineering and applies them to infrastructure and operations problems. (Google's implementation of DevOps).
*   **Chaos Engineering:** The discipline of experimenting on a system in order to build confidence in the system’s capability to withstand turbulent conditions in production (e.g., intentionally crashing servers to see if the system recovers).
*   **Toil:** Work that is manual, repetitive, automatable, tactical, devoid of enduring value, and that scales linearly as a service grows. SREs aim to eliminate toil.
*   **Error Budget:** The amount of error that your service can accumulate over a certain period of time before your users start being unhappy. If you have "budget" left, you can take risks; if not, you must freeze changes to focus on stability.
