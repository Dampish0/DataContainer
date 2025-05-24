Okay, I will go over the key concepts and keywords from each of the lectures you provided.

## Lecture 3: Object-Oriented Analysis & Design (OOD) & GRASP

This lecture introduces the fundamental principles of object-orientation and the basics of object-oriented analysis and design.

**Key Concepts & Keywords:**

*   **Object-Orientation (OO):**
    *   **Definition:** A mindset and a complete approach to software development that views reality (and thus software systems) as a collection of interacting objects. It's also a programming technique.
    *   **Means:** Instead of thinking about procedures and data separately, you think about "objects" that bundle data (attributes) and behaviors (methods) that operate on that data.

*   **Fundamental Object-Oriented Principles (The "A PIE" acronym):**
    *   **Abstraction:**
        *   **Definition:** Representing essential features of an object without including background details or explanations. A class is a simplified model (abstraction) of a real-world concept.
        *   **Means:** Focusing on what an object *is* and *does* at a high level, hiding unnecessary complexity. For example, a `Car` class might have `startEngine()` and `accelerate()` methods, abstracting away the complex mechanics involved.
    *   **Polymorphism:**
        *   **Definition:** The ability of an object to take on many forms. More practically, it means that a method call on an object reference can behave differently depending on the actual underlying object type.
        *   **Means:** You can write code that works with objects of a superclass type, and it will correctly call the appropriate method in any of its subclass objects. For example, a `Shape` class might have a `draw()` method, and subclasses like `Circle` and `Square` can implement `draw()` in their own specific ways.
    *   **Inheritance:**
        *   **Definition:** A mechanism where a new class (subclass or derived class) acquires the properties (attributes and methods) of an existing class (superclass or base class).
        *   **Means:** Promotes code reuse and establishes an "is-a" relationship (e.g., a `Dog` *is an* `Animal`). The subclass can extend or modify the inherited behavior.
    *   **Encapsulation:**
        *   **Definition:** Bundling data (attributes) and the methods that operate on that data within a single unit (a class), and restricting direct access to some of an object's components.
        *   **Means:** Protecting an object's internal state from outside interference by making attributes `private` and providing `public` methods (getters/setters or other interface methods) to access or modify the data. This helps in data hiding and maintaining the integrity of the object.

*   **Object-Oriented Analysis (OOA):**
    *   **Definition:** The process of identifying and describing the objects or concepts in the problem domain.
    *   **Means:** Understanding the real-world entities and their relationships relevant to the system being built. For example, in a flight information system, OOA would identify concepts like `Plane`, `Flight`, and `Pilot`.

*   **Object-Oriented Design (OOD):**
    *   **Definition:** The process of defining software objects and how they collaborate to fulfill the requirements identified during analysis.
    *   **Means:** Translating the concepts from OOA into a blueprint for software construction. This involves deciding on the attributes (e.g., `tailNumber` for a `Plane` object) and methods (e.g., `getFlightHistory()` for a `Plane` object) for each class, and how these objects will interact.

*   **Identifying Potential Objects:**
    *   **Method:** A common starting point is to find nouns in the problem specification (e.g., "customer," "rectangle," "area").
    *   **Refinement:**
        *   Differentiate between objects (which have state and behavior) and primitive data elements (e.g., `width`, `height` might be attributes of a `Rectangle` object rather than objects themselves).
        *   Determine which concepts are within the scope of the problem (e.g., "customer" or "program" might be out of scope for a simple rectangle calculator).

*   **GRASP (General Responsibility Assignment Software Patterns):**
    *   Mentioned in the outline but not detailed in the provided text. GRASP provides principles for assigning responsibilities to objects in OOD. You might need to consult other resources for details on specific GRASP patterns like Information Expert, Creator, Controller, Low Coupling, and High Cohesion.

---

## Lecture 5: Automated Testing - Unit Testing

This lecture focuses on the fundamentals of software testing, with a particular emphasis on unit testing.

**Key Concepts & Keywords:**

*   **Testing:**
    *   **Definition:** The process of evaluating a software item to detect differences between given input and expected output. Also, the process of evaluating software to ensure it meets specified requirements.
*   **Verification:**
    *   **Definition:** The process of determining whether the products of a phase of the software development process fulfill the requirements established during the previous phase.
    *   **Means:** "Are we building the product right?" Checking if the software conforms to its specification.
*   **Validation:**
    *   **Definition:** The process of evaluating software at the end of software development to ensure compliance with intended usage.
    *   **Means:** "Are we building the right product?" Checking if the software meets the customer's actual needs and expectations.

*   **Types of Testing (Categories):**
    *   **Based on Scope/Focus:** Functional, Unit, Integration, System, Acceptance, Performance, Security, Usability, etc.
    *   **Based on Scheduling:** When tests are run.
    *   **Based on Method:** Automated vs. Manual.
    *   **Based on Purpose:** New feature testing vs. Regression testing.
    *   **Based on Organization:** Who performs the tests.

*   **Functional Testing:**
    *   **Definition:** Testing the system to ensure it performs its intended functions as specified in the requirements. It verifies *what* the system does.

*   **Unit Testing:**
    *   **Definition:** Testing a specific, small, isolated piece of code (e.g., a method, function, or a small group of interacting them).
    *   **Isolation:** Unit tests are typically run without starting the whole application and usually do not interact with external dependencies like databases, filesystems, or networks directly.
    *   **Test Double:**
        *   **Definition:** A generic term for any kind of pretend object used in place of a real object for testing purposes.
        *   **Types:** Mocks, Stubs, Fakes, Spies, Dummies.
            *   **Mocks:** Objects that verify interactions (e.g., "was this method called with these arguments?").
            *   **Stubs:** Objects that provide predefined responses to calls made during the test.
    *   **Sociable vs. Solitary Unit Tests:**
        *   **Solitary:** Tests that isolate the unit under test from its collaborators by using test doubles for all dependencies.
        *   **Sociable:** Tests that allow the unit under test to interact with its real collaborators (other genuine classes), as long as they are part of the same logical unit and don't cross significant boundaries (like network or database).

*   **Unit Testing Principles (Examples):**
    *   **Simplicity:** Tests should be simple and easy to understand.
    *   **Readability and Comprehension:** Test code should be as readable as production code.
    *   **Test Behaviour (not implementation):** Tests should verify the observable behavior of a unit, not how it internally achieves that behavior. This makes tests less brittle to refactoring.
    *   **A test should fail:** Write tests that can actually fail if the code is broken.
    *   **4-phase test design (Arrange, Act, Assert, Teardown/Cleanup):**
        *   **Setup/Arrange:** Initialize objects and set up preconditions.
        *   **Execution/Act:** Call the method or code being tested.
        *   **Validation/Assert:** Check if the outcome is as expected.
        *   **Tear-down/Cleanup:** Release resources (less common in modern unit testing frameworks with garbage collection).

*   **Feature Testing:**
    *   **Definition:** Testing to ensure that a specific functionality is implemented as expected and meets the real needs of users.
    *   **Includes:**
        *   **Interaction Tests:** Verify that interfaces (UI, API) behave according to specifications.
        *   **Usefulness Tests:** Check if the feature implements what users are likely to want.
    *   Often involves **Integration Testing** or **Component Testing** (testing interactions between components).

*   **System Testing:**
    *   **Definition:** Testing the system as a whole, rather than individual features or components.
    *   **Focus:**
        *   Unexpected and unwanted interactions between parts of the system.
        *   Ensuring features work together effectively.
        *   Verifying the system operates as expected in different environments.
        *   Checking quality attributes like recovery, security.
    *   **Types:**
        *   **Scenario-Based Testing:** Testing end-to-end pathways or user scenarios.
        *   **Requirements-Based Testing:** Validating that the system has properly implemented its requirements.

*   **Integration Testing:**
    *   **Definition:** Testing the interfaces and interactions between integrated components or systems.
    *   **Importance:** Unit tests can pass for individual components, but the system can still fail if these components don't work together correctly.

*   **Regression Testing:**
    *   **Definition:** Re-running existing tests after modifications to the software to ensure that changes (e.g., bug fixes, new features) have not adversely affected existing functionality or reintroduced old bugs.
    *   **Best Practice:** Automate regression tests. When a bug is found, write a test case that exhibits the bug, fix the bug, and then keep the test to ensure it doesn't reappear.

*   **Test Automation:**
    *   **Definition:** Using software tools to execute tests and compare actual outcomes with predicted outcomes.
    *   **Aspects:** Test generation, execution, analysis.

---

## Lecture 6: Continuous Integration (CI)

This lecture introduces the concept and practices of Continuous Integration.

**Key Concepts & Keywords:**

*   **Continuous Integration (CI):**
    *   **Definition:** A software development practice where members of a team merge their code changes into a shared repository frequently, ideally at least daily. Each merge (or commit) triggers an automated build and test sequence.
    *   **Goal:** To detect integration errors as quickly as possible, improve collaboration, and streamline the release process.
    *   **Focus:** The build and unit testing stages of the software release process.

*   **Typical Development Workflow (without CI):** Often involves developers working in isolation for longer periods, leading to complex and difficult merges ("integration hell").

*   **CI Servers (Build Servers):**
    *   **Definition:** Software tools that automate the CI process. They monitor the version control repository for changes, and when changes are detected, they automatically build the software and run tests.
    *   **Examples:** Jenkins, GitLab CI, Travis CI, CircleCI, GitHub Actions.

*   **GitHub Actions:**
    *   **Definition:** A CI/CD (Continuous Integration/Continuous Delivery or Deployment) platform provided by GitHub that allows you to automate your build, test, and deployment pipeline directly within your GitHub repository.

*   **Components of GitHub Actions:**
    *   **Workflows:**
        *   **Definition:** A configurable automated process made up of one or more jobs. Defined by a YAML file (e.g., `.github/workflows/main.yml`) in your repository.
        *   **Triggered by:** Events in the repository (e.g., push, pull request), manually, or on a schedule.
    *   **Events:**
        *   **Definition:** Specific activities in a repository that trigger a workflow run (e.g., `push` to a branch, `pull_request` creation, `schedule`).
    *   **Jobs:**
        *   **Definition:** A set of steps in a workflow that execute on the same runner. Steps within a job are executed in order and can depend on each other.
    *   **Actions:**
        *   **Definition:** Custom applications or reusable units of code for the GitHub Actions platform that perform complex but frequently repeated tasks (e.g., `actions/checkout` to check out code, `actions/setup-node` to set up Node.js). Can be created by the community or by yourself.
    *   **Runners:**
        *   **Definition:** A server (virtual machine) that runs your workflows when they’re triggered. Each runner can run a single job at a time.
        *   **Types:** GitHub-hosted (Ubuntu Linux, Microsoft Windows, macOS) or self-hosted.

*   **Workflow File:**
    *   **Syntax:** YAML (`.yml` or `.yaml` extension).
    *   **Location:** Typically in the `.github/workflows` directory of your repository.

*   **Configuration Management:**
    *   **Definition:** The process by which all artifacts relevant to your project (code, documentation, configuration files, dependencies, etc.), and the relationships between them, are stored, retrieved, uniquely identified, and modified in a controlled manner.
    *   **Relevance to CI:** CI relies on good configuration management, especially version control, to manage code changes and ensure reproducible builds.

*   **Build Systems (Build Automation):**
    *   **Definition:** The process of scripting or automating the compilation of computer source code into binary code (executables, libraries) and other artifacts needed for deployment or execution.
    *   **Tools:** Examples include Make, Ant, Maven, Gradle (for Java), MSBuild (for .NET), npm/yarn scripts (for JavaScript), pip (for Python package management which is part of a build/deploy process).
    *   **Role in CI:** The CI server uses a build system to perform the build and test steps.

---

## Lecture 8: Agile Methods

This lecture discusses agile methodologies in software development.

**Key Concepts & Keywords:**

*   **Successful Project Criteria:**
    *   OnTime, OnBudget, OnTarget (meets requirements), OnGoal (delivers value and satisfaction).

*   **Common Reasons for Project Failure:**
    *   Unrealistic goals, inaccurate estimates, badly defined requirements, poor reporting, unmanaged risks, poor communication, immature technology, inability to handle complexity, sloppy development practices, poor project management, stakeholder politics, commercial pressures.

*   **Problems with Traditional Software Development:**
    *   Customers often don't know exactly what they need or want initially.
    *   Requirements change frequently (customer minds, priorities).
    *   Difficult to satisfy diverse stakeholders.
    *   Hard to specify requirements completely and accurately upfront.
    *   Poor estimation of software tasks.
    *   Unpredictable events ("stuff happens").
    *   Iterative refinement is often needed ("takes several times to get something right").
    *   Users often realize what they want only after seeing a version of the product.
    *   Difficult to identify the most important features (80/20 rule) before deployment.
    *   Hard to account for unknown factors.

*   **Agile Manifesto (Core Values):**
    *   **Origin:** Created in 2001 by a group of software developers.
    *   **Nature:** "Agile" is described as a value system, not a specific process.
    *   **The Four Values:**
        1.  **Individuals and interactions** over processes and tools
            *   **Means:** Valuing skilled people and effective communication more than rigid processes or specific tools.
        2.  **Working software** over comprehensive documentation
            *   **Means:** Prioritizing the delivery of functional software that provides value, rather than spending excessive time on detailed documentation that might quickly become outdated. Some documentation is still necessary.
        3.  **Customer collaboration** over contract negotiation
            *   **Means:** Fostering a continuous partnership with the customer throughout the development process, rather than relying solely on initial contract terms.
        4.  **Responding to change** over following a plan
            *   **Means:** Embracing changes in requirements as an opportunity to provide more value, rather than strictly adhering to an initial plan that may no longer be relevant. This doesn't mean no planning, but that plans are adaptable.
    *   **Key Phrase:** "That is, while there is value in the items on the right, we value the items on the left more."

*   **12 Principles behind the Agile Manifesto (First few mentioned in the text):**
    1.  **Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.**
        *   **Means:** Focus on delivering working software in small, frequent increments that the customer can use and provide feedback on.
    2.  **Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.**
        *   **Means:** Be flexible and adapt to new or modified requirements as they emerge, viewing them as opportunities to improve the product.
    3.  **Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.**
        *   **Means:** Short development cycles (iterations or sprints) allow for regular feedback and course correction.
    4.  **(The text cuts off here, but the fourth principle is: Business people and developers must work together daily throughout the project.)**
        *   **Means:** Close collaboration between the development team and business stakeholders ensures alignment and quick resolution of questions.

*   **Scrum:**
    *   Mentioned in the outline (Scrum definition, Theory, Values, Team, Events, Artefacts) but not detailed in the provided text. Scrum is a popular agile framework for managing and completing complex projects. You'll need to consult other resources for details on Scrum roles (Product Owner, Scrum Master, Development Team), events (Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective), and artifacts (Product Backlog, Sprint Backlog, Increment).

---

## Lecture 10: DevOps

This lecture introduces the concept, principles, and culture of DevOps.

**Key Concepts & Keywords:**

*   **History of DevOps:**
    *   **Origin:** Began around 2007 due to concerns about the traditional software development model where development (Dev) and IT operations (Ops) teams worked in silos.
    *   **Problem Addressed:** Agile methodologies improved development, but a gap often remained between developers and the operations team responsible for production environments, leading to inefficiencies and lack of collaboration.

*   **DevOps:**
    *   **Definition:** A set of practices, tools, and a cultural philosophy that automate and integrate the processes between software development (Dev) and IT operations (Ops) teams.
    *   **Emphasis:** Team empowerment, cross-team communication and collaboration, and technology automation.
    *   **More than tools/practices:** It's a **mindset** and a **cultural shift** where teams adopt new ways of working.

*   **DevOps Culture:**
    *   **Developer Perspective:** Developers get closer to the user, understanding their requirements and needs better.
    *   **Operations Perspective:** Operations teams get involved earlier in the development process, contributing maintenance requirements and customer needs.
    *   **Goal:** Deliver applications and services at a faster pace and higher quality than traditional models.

*   **Key DevOps Principles:**
    1.  **Collaboration:**
        *   **Core Idea:** Development and operations teams (and often other teams like QA and security) coalesce into functional teams that communicate, share feedback, and collaborate throughout the entire development and deployment lifecycle.
        *   **Outcome:** Often leads to merged teams or single teams owning a feature/project from idea to delivery ("full stack" responsibility), resulting in higher quality due to increased ownership.
    2.  **Automation:**
        *   **Core Idea:** Automate as much of the software development lifecycle (SDLC) as possible – from building and testing to deployment and infrastructure provisioning.
        *   **Benefits:** Frees up developers' time, reduces human errors, increases team productivity, and is a key element of CI/CD pipelines.
    3.  **Continuous Improvement:**
        *   **Core Idea:** A practice of ongoing experimentation, minimizing waste (e.g., time, resources), and optimizing for speed, cost, and ease of delivery. Derived from agile practices and lean manufacturing.
        *   **Connection to Continuous Delivery:** Allows teams to continuously push updates that improve software systems, eliminate waste, and bring more customer value.
    4.  **Customer-centric action:**
        *   **Core Idea:** Use short feedback loops with customers and end-users to develop products and services centered around their actual needs and requirements.
        *   **Means:** Actively seek and incorporate customer feedback to guide development and ensure the product delivers value.
    5.  **Create with the end in mind:**
        *   **Core Idea:** Consider the entire lifecycle of the application or service from the very beginning of development, including deployment, operations, monitoring, and maintenance.
        *   **Means:** Developers and operations teams work together to design systems that are not only functional but also operable, scalable, and maintainable in production.

*   **DevOps Lifecycle & Toolchain:**
    *   Mentioned in the outline but not detailed in the provided text. The DevOps lifecycle typically includes phases like plan, code, build, test, release, deploy, operate, and monitor, supported by a toolchain (a set of integrated tools) for each phase.

---

## Lecture 11: Automated Testing (Continued)

This lecture expands on automated testing concepts, including integration testing, BDD, and non-functional testing.

**Key Concepts & Keywords:**

*   **Unit Testing (Recap):**
    *   Testing a specific piece of code in isolation.

*   **Integration Testing (Component Testing):**
    *   **Definition:** Tests the behavior of several components of your application working together. These tests may interact with external systems like databases or filesystems.
    *   **Tools:** Unit testing libraries can be useful. For multi-service programs, threading/multiprocess management libraries might be needed.

*   **System Testing:**
    *   **Definition:** Testing the system as a whole, rather than individual features.
    *   **Focus:**
        *   Unexpected and unwanted interactions.
        *   Ensuring features work together effectively.
        *   Verifying operation in different environments.
        *   Checking quality attributes (e.g., recovery, security).

*   **Acceptance Testing:**
    *   **Definition:** Tests that the application meets the criteria decided by the business (or customer/user), including functionality and characteristics like capacity, availability, and security.
    *   **How:** Can be manual, automated, or semi-automated, depending on the system and language.

*   **Test Automation Tools (Examples):**
    *   Kobiton, Katalon Studio, Selenium, UFT (Unified Functional Testing), TestComplete, LambdaTest, TestProject, Cucumber, SpecFlow.
    *   **BDD Testing Tools:** Cucumber, SpecFlow.

*   **Behaviour-Driven Development (BDD):**
    *   **Definition:** An evolution of Test-Driven Development (TDD) where the focus of testing is the expected *behavior* of the system from a user's perspective.
    *   **Specification:** Behaviors are specified using a Domain-Specific Language (DSL), often in a "Given-When-Then" format (Gherkin syntax).
        *   **Given:** Some initial context (preconditions).
        *   **When:** An event occurs (action).
        *   **Then:** Ensure some outcomes (expected results).
    *   **Process:** Story (user requirement) -> Scenarios (acceptance criteria written in Gherkin) -> Automated Tests (that implement these scenarios).
    *   **Example Scenario (Account is in credit):**
        *   **Given** the account is in credit
        *   **And** the card is valid
        *   **And** the dispenser contains cash
        *   **When** the customer requests cash
        *   **Then** ensure the account is debited
        *   **And** ensure cash is dispensed
        *   **And** ensure the card is returned

*   **Non-Functional Testing:**
    *   **Definition:** Testing aspects of the software that are not related to specific functions or user actions, but rather to how the system operates.
    *   **Categories:**
        *   **Performance / Throughput Tests:** How responsive and stable the system is under a particular workload.
        *   **Capacity Tests:** How much load the system can handle before performance degrades.
        *   **Security Tests:** How well the system protects against unauthorized access, data breaches, etc.

*   **Performance Testing:**
    *   **Definition:** A type of testing intended to determine the responsiveness, throughput, reliability, and/or scalability of a system under a given workload.
    *   **Types:**
        *   **Load Testing:** Simulating expected user load to see how the system performs.
        *   **Stress Testing:** Pushing the system beyond its normal operating limits to see how it behaves and when it breaks.
        *   **Spike Testing:** Observing system behavior when subjected to sudden, massive increases in load.
        *   **Chaos Testing (Chaos Engineering):** Experimenting on a system in production to build confidence in its capability to withstand turbulent conditions.
    *   **Performance Monitor Metrics (Examples):**
        *   Physical disk (I/O, queue length)
        *   Memory (usage, page faults)
        *   Processor (CPU utilization)
        *   Network (bandwidth, latency)

This covers the main points and keywords from the lecture notes you provided. Remember to also review any examples or diagrams from the original lectures, as they can provide further context. Good luck with your exam!






**Key Points for Multiple Choice Exams**

---

### Object-Oriented Analysis & Design (OOD) & GRASP

- **Object-Orientation:** Views systems as interacting objects bundling data and behavior.
- **A PIE Principles:**  
  - **Abstraction:** Focus on essential features, hide complexity.
  - **Polymorphism:** Same interface, different implementations.
  - **Inheritance:** Subclasses inherit from superclasses ("is-a" relationship).
  - **Encapsulation:** Hide internal state, expose via methods.
- **OOA:** Identify real-world objects/concepts in the problem domain.
- **OOD:** Define software objects and their interactions.
- **Identifying Objects:** Look for nouns in requirements; refine to find true objects.
- **GRASP:** Patterns for assigning responsibilities (e.g., Information Expert, Creator).

---

### Automated Testing - Unit Testing

- **Testing:** Detects differences between actual and expected output.
- **Verification:** "Are we building the product right?" (meets specs)
- **Validation:** "Are we building the right product?" (meets needs)
- **Types of Testing:** Unit, Integration, System, Acceptance, Regression, etc.
- **Unit Testing:** Tests small, isolated code units; uses test doubles (mocks, stubs).
- **Solitary vs. Sociable Tests:** Solitary isolates dependencies; sociable uses real collaborators.
- **Unit Test Principles:** Simplicity, readability, test behavior not implementation, tests must fail if code is broken.
- **4-Phase Test:** Arrange, Act, Assert, Teardown.
- **Regression Testing:** Re-run tests after changes to catch reintroduced bugs.
- **Test Automation:** Use tools to run and check tests automatically.

---

### Continuous Integration (CI)

- **CI:** Frequently merge code to shared repo; each merge triggers automated build/test.
- **Goal:** Detect integration errors early, streamline releases.
- **CI Servers:** Automate builds/tests (e.g., Jenkins, GitHub Actions).
- **GitHub Actions:** Automate workflows in GitHub repos (YAML files, runners, jobs, actions).
- **Configuration Management:** Controls and tracks all project artifacts.
- **Build Systems:** Automate compiling and packaging code (e.g., Maven, Gradle).

---

### Agile Methods

- **Success Criteria:** OnTime, OnBudget, OnTarget, OnGoal.
- **Common Failures:** Unrealistic goals, poor requirements, unmanaged risks, bad communication.
- **Problems with Traditional Methods:** Changing requirements, poor estimation, hard to specify needs upfront.
- **Agile Manifesto Values:**
  1. Individuals/interactions > processes/tools
  2. Working software > documentation
  3. Customer collaboration > contract negotiation
  4. Responding to change > following a plan
- **Agile Principles:** Early/frequent delivery, welcome change, short iterations, close collaboration.
- **Scrum:** Agile framework (roles, events, artifacts).

---

### DevOps

- **DevOps:** Combines Dev and Ops for faster, higher-quality delivery.
- **Culture:** Collaboration, automation, continuous improvement, customer focus, consider full lifecycle.
- **Principles:**  
  1. Collaboration (cross-team)
  2. Automation (CI/CD, infrastructure)
  3. Continuous improvement (optimize, experiment)
  4. Customer-centric action (short feedback loops)
  5. Create with end in mind (design for operations/maintenance)
- **Lifecycle:** Plan, code, build, test, release, deploy, operate, monitor.

---

### Automated Testing (Continued)

- **Integration Testing:** Tests multiple components together, may use real external systems.
- **System Testing:** Tests the whole system for interactions and quality attributes.
- **Acceptance Testing:** Checks if system meets business/user criteria.
- **Test Automation Tools:** Selenium, Cucumber, etc.
- **BDD:** Focus on system behavior; uses "Given-When-Then" scenarios (Gherkin syntax).
- **Non-Functional Testing:** Performance, capacity, security.
- **Performance Testing Types:** Load, stress, spike, chaos testing.
- **Metrics:** Disk I/O, memory, CPU, network.

---

**Tip:** Know definitions, differences between test types, core agile/DevOps values, and the meaning of OOP principles.
