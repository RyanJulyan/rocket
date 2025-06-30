# Functional Testing Report Template

### Introduction

This Functional Testing Report provides a comprehensive overview of the testing activities and results for the {{project_name}}. It encompasses various aspects of testing, including [unit testing](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/02_functional_testing_report_template.md#unit-testing), [user acceptance testing (UAT)](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/02_functional_testing_report_template.md#user-acceptance-testing-uat), [load testing](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/02_functional_testing_report_template.md#load-testing), [integration testing](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/02_functional_testing_report_template.md#integration-testing-and-data-pipelines), and [security testing](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/02_functional_testing_report_template.md#security-testing-and-standards). The primary purpose of this document is to systematically record the testing methodologies, procedures, results, and recommendations to ensure that the {{project_name}} meets its designated requirements and quality standards.

The scope of this report covers the entire testing lifecycle of the project, from the initial unit tests to the final stages of security testing. It aims to provide a clear and concise understanding of the testing process, the tools used, the challenges encountered, and the measures taken to ensure the functionality, reliability, performance, and security of the {{project_name}}.

This report is intended for a broad range of stakeholders, including the development team, QA team, project managers, security specialists, and the client representative. It serves as a vital document for understanding the quality and robustness of the {{project_name}}, facilitating informed decision-making for future developments and enhancements.

## {{project_name}}:

### Revision History:
| Version number | Date Changed   | Brief Description of Changes |
|----------------|----------------|------------------------------|
| 1              | 2023/11/10     | Created Template             |

### Document Approval Details:
| Client Name                                                    | Current Role                                                   | Section Responsible for                      |
|----------------------------------------------------------------|----------------------------------------------------------------|----------------------------------------------|
| {{client_unit_testing_name}}                                   | {{client_unit_testing_role}}                                   | Unit Testing                                       |
| {{client_uat_name}}                                            | {{client_uat_role}}                                            | User Acceptance Testing (UAT)                                         |
| {{client_load_testing_name}}                                   | {{client_load_testing_role}}                                   | Load Testing                                       |
| {{client_integration_testing_name}}                                   | {{client_integrationtesting_role}}                                   | Integration Testing                                       |
| {{client_security_testing_and_standards_name}}                                   | {{client_security_testing_and_standards_role}}                                   | Security Testing and Standards                                       |

### Functional Testing Overview:
- **Purpose:** [State the objectives of functional testing]
- **Scope:** [Define the scope of testing, including which features and components will be tested]


### Unit Testing:
- **Methodology:**
    - [ ] **Framework:** Utilize Python's [pytest](https://pypi.org/project/pytest/) framework for writing and executing unit tests.
    - [ ] **Isolation:** Ensure unit tests are isolated, testing one component at a time.
    - [ ] **Test Driven Development (TDD):** Follow TDD practices where tests are written prior to writing the actual code.
        - [ ] **Peer Programming:**
            - _Use Hassan style_: One person writes the test, another person implements the code
- **Standards:**
    - [ ] **File nameing conventions:**
        > File names should be the higher level function name `test_{{function_name}}.py` allowing for multiple tests to be included in a single file.
        - Consider separating out:
            - Functions 
            - Classes
    - [ ] **Naming Conventions of Tests:**
        > Test names should be descriptive and indicate what the test is supposed to do. Naming conventions for test functions are crucial for readability and maintainability of your test suite. The format you've provided is quite descriptive and is a variation of a common approach. The general idea is to make the test name itself as descriptive as possible, so that when it fails, you can have a good idea of what might have gone wrong without even looking at the test code. A commonly used naming convention is `test_{{function_name}}_given_{{conditions}}_expect_{{what_is_being_tested}}` which is quite explicit and follows the Given-When-Then style, which is popular in Behavior-Driven Development (BDD). For example, `test_add_given_positive_numbers_expect_correct_sum` for a test that checks an addition operation. This makes it clear what the test is doing:
        - `test_`: Prefix to indicate that it's a test function (required for frameworks like unittest and pytest to recognize it as a test).
        - `{{function_name}}`: The name of the function or method that you're testing.
        - `given_{{conditions}}`: The conditions or context in which the test is run.
        - `expect_{{what_is_being_tested}}`: What you are actually testing; the expected outcome or behavior. 
    - [ ] **Structure of a Unit Test:**
        - Unit tests generally follow the "Three A's" pattern: Arrange, Act, and Assert, with the addition of mocks before the "Arrange" phase. For more details on "The Three A's", you can refer to [The Three A's of Unit Testing](https://dev.to/coderjay06/the-three-a-s-of-unit-testing-b22).
            - **Fixtures**: Use fixtures to set up any preconditions for your test, like database connections or configuration settings.
            - **Mocks**: Use mocks to isolate the unit of work from external dependencies or services.
            - **Arrange**: Set up the objects and variables to be tested.
            - **Act**: Perform the action that you want to test.
            - **Assert**: Check that the action has the expected outcome.
    - **Quickstart:** [Pytest Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/pytest_quickstart.md)
- [ ] **Test Cases and Coverage:**
    - **API Endpoint Testing:** Write test cases for each API endpoint, testing for expected responses, error handling, and edge cases.
    - **ML Model Testing:** Test machine learning models for accuracy, overfitting, and underfitting. Use libraries like `scikit-learn` for model testing.
    - **AI Algorithm Testing:** Test AI algorithms for correctness, efficiency, and expected behavior under various scenarios.

| Module Name | Test Case ID | Test Case Name | Conditions       | Assertions       | Mocks            | Coverage Metrics | Status   | Run Date   |
|-------------|--------------|----------------|------------------|------------------|------------------|------------------|----------|------------|
| ...         | UT-[...]     | ...            | ...              | ...              | ...              | ...              | ...      | YYYY/MM/DD |

- [ ] **Results:**
    - Utilize Continuous Integration (CI) tools to automatically run unit tests and report results.
    - Monitor for high pass rates and address any failing tests promptly.
- [ ] **Issues and Resolutions:**
    - Document any issues encountered during testing, including bugs in logic, performance issues, or integration problems, and track their resolution.
    - [ ] Use the [Change Request Template](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/03_change_request_template.md) to manage these changes


### User Acceptance Testing (UAT):
- [ ] **UAT Plan:**
    - **Objectives:** Define clear objectives focusing on end-user requirements and the usability of the API, ML, and AI components.
    - **Success Criteria:** Establish criteria for successful UAT, such as specific user tasks being completed efficiently.

| Module Name | Test Case ID | Test Case Name | Conditions       | Expectations     | Results          | Status   | Test Date  |
|-------------|--------------|----------------|------------------|------------------|------------------|----------|------------|
| ...         | UAT-[...]    | ...            | ...              | ...              | ...              | ...      | YYYY/MM/DD |
- [ ] **UAT Procedures:**
    - **Feedback Mechanism:** Implement a structured feedback mechanism to gather detailed user responses.
        - [ ] Use the [UAT Feedback Template](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/05_uat_feedback_template.md) to manage the feedback
    - **Participant Selection:** Choose a diverse group of users, representative of the end-users.

| Client Name      | Current Role      | Test Case ID | Test Case Name |
|------------------|-------------------|--------------|----------------|
| {{client_name}}   | {{client_role}}  | UAT-[...]    | ...            |
- [ ] **User Testing Sessions:**
    - Schedule planning sessions and get some key users invloved in the structure and examples of user testing sessions.
        - Conduct structured sessions where users interact with the system, focusing on real-world use cases.
            - Try allow the client users to run and explain some of the application
        - [ ] Use the [UAT Agenda Template](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/04_uat_session_agenda_template.md) to manage the feedback
- **Feedback & Iterations:**
    - [ ] Analyze feedback for trends and common issues.
    - [ ] Use the [Change Request Template](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/03_change_request_template.md) to manage these changes
        - Iterate on the API, ML models, and AI algorithms based on this feedback.

### Load Testing:
- [ ] **Load Testing Strategy:**
    - **Tools:** Utilize [JMeter](https://jmeter.apache.org/) for simulating user traffic to the API.
    - **Scenarios:** Design scenarios that mimic real-world usage, including high traffic and peak usage times.
        - Use `JMeter`'s CSV functionality to ensure that the tests are repeatable and scalable
    - **Quickstart:** [JMeter Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/j_meter_quickstart.md)
- [ ] **Performance Benchmarks:**
    - Establish benchmarks for response times, throughput, and error rates.
    - Use profiling tools like to identify bottlenecks in the code:
        - For Project-Level Profiling use: [Scalene](https://github.com/plasma-umass/scalene)
            - **Description**: A high-resolution, low-overhead profiler that measures CPU, GPU, and memory usage.
            - **Quickstart:** [Scalene Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/scalene_quickstart.md)
        - For Function-Level Profiling use: [Python timeit](https://docs.python.org/3/library/timeit.html)
            - **Description:** A Python library for measuring the execution time of small bits of Python code. It has both a Command-Line Interface and a callable one.
            - **Quickstart:** [timeit Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/timeit_quickstart.md)
- [ ] **Performance Metrics:**
    - Specific performance metrics that were tested:
        - Response time under load
        - Concurrency
        - System stability

| Test Case Name | Endpoint         | Conditions File  | Scale Up Time    | Scale Up To      | Expected Response time | Actual Response time | System Stability |
|----------------|------------------|------------------|------------------|------------------|------------------------|----------------------|------------------|
| ...            | ...              | ...              | ...              | ...              | ...                    | ...                  | ...              |

- **Results & Optimization:**
    - Analyze test results to identify areas for performance optimization.
    - Implement caching, query optimization, or other techniques to improve performance.


### Integration Testing and Data Pipelines
- **Key considerations:** 
    - [ ] **Volume Testing:**
        - **Goal:** Assess how the pipeline handles large volumes of data.
        - **Method:** Ingest a significantly large dataset into the pipeline and monitor its ability to process this data efficiently.
    - [ ] **Velocity Testing:**
        - **Goal:** Evaluate the pipeline's performance with rapid data ingestion.
        - **Method:** Gradually increase the data ingestion rate and observe the pipeline's throughput and latency.
    - [ ] **Variety Testing:**
        - **Goal:** Ensure the pipeline can handle different types of data (structured, semi-structured, unstructured).
        - **Method:** Test with diverse datasets to assess the pipeline's flexibility and robustness.
    - [ ] **Concurrency Testing:**
        - **Goal:** Determine the pipeline's performance under simultaneous operations.
        - **Method:** Run multiple data processing tasks concurrently and monitor for issues like resource contention or performance degradation.
- **Tools and Techniques:**
    - [ ] **Performance Monitoring Tools:**
        - Utilize generic monitoring tools that can track metrics such as CPU usage, memory consumption, I/O operations, and throughput. Tools like Grafana, Prometheus, or even cloud-specific monitoring solutions can be employed.
    - [ ] **Custom Scripts and Simulators:**
        - Develop scripts (e.g., in Python, Bash, or using cloud CLI tools) to automate the generation of test data and simulate operational loads.
    - [ ] **Data Generation Tools:**
        - Use tools like Apache JMeter, TPC (Transaction Processing Performance Council) benchmarks, or custom data generators to create realistic test data and load scenarios.
    - [ ] **Integration with APIs:**
        - If your data pipeline interacts with external APIs, test these integrations under stress conditions using tools like Postman, Apache JMeter, or custom scripts.
- **Steps for Integration Testing:**
    - [ ] **Environment Preparation:**
        - Set up a dedicated testing environment that mimics your production environment as closely as possible.
    - [ ] **Data Preparation:**
        - Create or obtain test datasets that cover the necessary volume, velocity, and variety aspects.
    - [ ] **Monitoring and Alerting Setup:**
        - Configure comprehensive monitoring and alerting to track performance metrics and identify bottlenecks.
    - [ ] **Execution of Tests:**
        - Run your tests, gradually increasing the load and observing the system's behavior. This includes ingesting large data sets, executing complex queries, and running concurrent operations.
    - [ ] **Result Analysis:**
        - Analyze the test results to identify performance bottlenecks, resource limitations, and other issues that might impact scalability and reliability.
    - [ ] **Iterative Optimization:**
        - Use the insights from the stress tests to optimize the pipeline. This could involve tuning configurations, optimizing data models, or improving processing logic.
- **Additional Considerations:**
    - [ ] **Cost Management:** Be aware of the potential costs associated with high-volume processing, especially in cloud environments.
    - [ ] **Data Security:** Ensure that test data is secure and compliant with data protection regulations.
    - [ ] **Documentation:** Maintain thorough documentation of the testing methodology, configurations used, and findings for future reference and compliance purposes.


### Security Testing and Standards:
- **Security Testing Methodology, Approach and Phases:**
    - [ ] **Planning Phase:** Identifying key assets, defining security requirements, and establishing testing goals.
    - [ ] **Threat Modeling:** Creating a threat model to identify potential security threats and vulnerabilities.
    - [ ] **Test Planning:** Developing a detailed security testing plan, including tools, techniques, and schedules.
    - [ ] **Execution Phase:** Conducting the security tests as per the plan.
    - [ ] **Analysis Phase:** Analyzing test results to identify security flaws and vulnerabilities.
    - [ ] **Reporting and Feedback:** Documenting findings and providing actionable recommendations.
- **Basic Principles:**
    - Always **prioritize security** in all aspects of development.
    - [ ] **Regularly update packages and dependencies.**
    - [ ] **Encrypt sensitive data both in transit and at rest.**
    - **Secret Management:**
        - [ ] **Python-dotenv;**
            - Use [Python-dotenv](https://pypi.org/project/python-dotenv/) for managing `.env` files.
        - [ ] **Secrets Vault:**
            - For storing secrets in a more secure manner, consider using a secrets vault.
        - [ ] **Basic Principles:**
            - [ ] Never commit secrets to the repository.
            - [ ] Use environment-specific configuration files for managing secrets.
        - **Stop Using `.env` Files for _Everything_:**
            - Follow the guidelines from this [dev.to article](https://dev.to/gregorygaines/stop-using-env-files-now-kp0) which suggests not using `.env` files for everything. Instead, `.env` files should only be used for API keys and environment variables for the secrets vault.
    - [ ] Follow the **[OWASP Top Ten](https://owasp.org/www-project-top-ten/)** as a foundational framework for security testing. The OWASP Top Ten provides a list of the most critical web application security risks and how to mitigate them.
        - For a practical understanding of penetration testing, consider watching [this YouTube video](https://www.youtube.com/watch?v=YYe0FdfdgDU) which provides a hands-on demonstration.
- **Trusting Your Workspace:**
    - Follow the guidelines from the [VS Code documentation](https://code.visualstudio.com/docs/devcontainers/containers#_trusting-your-workspace) to trust your workspace.
- **Security Testing Strategy:**
    - **Purpose and Scope:**
        - Outlining the specific objectives and scope of security testing, focusing on identifying and mitigating security vulnerabilities within the API, ML, and AI components.
    - **Testing Methods:**
        - [ ] **Static Application Security Testing (SAST):** Utilizing tools to analyze source code for potential security vulnerabilities.
            - [ ] **Complexity Index:**
                - Use [Flake8](https://pypi.org/project/flake8/) to measure the complexity of the code; aim for a score below 12
            - [ ] **Static Code Analysis:**
                - [ ] **Local:** Use [MyPy](https://mypy.readthedocs.io/en/stable/getting_started.html) for type checking and static code analysis
                - [ ] **CI/CD:** Use [SonarQube](https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/) for type checking and static code analysis in the ID
            - [ ] **Linting:**
                - Use [Black](https://pypi.org/project/black/) for code formatting
            - [ ] **Type Hinting:**
                - Always use type hints for function arguments and return types at the top level
                - use the standary `typing` library for type hints
        - [ ] **Dynamic Application Security Testing (DAST):** Conducting tests on running applications to identify real-time security issues.
            > **_Remember, any penetration testing tools like `Metasploit `, `Burp Suite` and `OWASP ZAP` are powerful and should be used responsibly and legally. Always have explicit and documented permission to test a website before using a tool like ZAP for security testing._**
            - [ ] [Metasploit Framework](https://www.metasploit.com/) is the industry-standard platform for developing, testing, and executing exploits. It bundles thousands of ready-made modules and an interactive console, making it a staple for penetration testers, red teams, and security researchers.
                - **Key Capabilities of Metasploit Framework:**
                    - **Exploit Modules:** Thousands of exploits for OS, network, and application weaknesses—with automatic payload selection.
                    - **Payload & Encoder Library:** Generate and obfuscate shellcode (e.g., `msfvenom`) for Windows, Linux, macOS, Android, and more.
                    - **Meterpreter Shell:** In-memory post-exploitation environment offering file system, privilege escalation, pivoting, and more.
                    - **Auxiliary & Scanner Modules:** Port scans, service enumeration, brute-force logins, fuzzing, and DoS testing.
                    - **Post-Exploitation Modules:** Gather credentials, dump hashes, capture screenshots, pivot to new subnets, and maintain persistence.
                    - **Evasion & Anti-Forensics:** Built-in encoders, packers, and the ability to stage payloads in memory to bypass basic AV/EDR.
                    - **Database & Workspaces:** Store hosts, services, and loot; track findings across engagements with `msfdb`.
                    - **Automation & APIs:** Scriptable via `msfconsole`, RPC/REST interfaces, and integration with tools like Nmap, Nessus, and Armitage.
                    - **Community & Modularity:** Active open-source ecosystem—easy to write custom modules and share them on GitHub.
                - **Quickstart:** [Metasploit Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/metasploit_quickstart.md)
            - [ ] [Burp Suite Community Edition](https://portswigger.net/burp/communitydownload) is a widely used tool for web security testing. It's popular among penetration testers and ethical hackers for its rich feature set and user-friendly interface.
                - **Key Capabilities of Burp Suite Community Edition:**
                    - **Proxy Tool:** Allows interception, inspection, and modification of raw traffic passing between your browser and the web server.
                    - **Scanner:** Automated scanner (limited in the Community Edition) to identify vulnerabilities in web applications.
                    - **Intruder:** A powerful tool for carrying out customized attacks to find and exploit unusual vulnerabilities.
                    - **Repeater:** Modify and resend individual requests, and analyze the responses.
                    - **Sequencer:** Analyzes the quality of randomness in an application’s session tokens.
                    - **Comparer:** Compares application data like request/response pairs, highlighting the differences.
                    - **Extensibility:** Ability to extend functionality using the Burp Extender.
                - **Quickstart:** [Burp Suite Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/burp_suite_quickstart.md)
            - [ ] [OWASP ZAP](https://www.zaproxy.org/download/) is a powerful penetration testing tool for finding vulnerabilities in web applications. It is designed to be used by both those new to application security as well as professional penetration testers.
                - **Key Capabilities of OWASP ZAP:**
                    - **Automated Scanner:** Scans for vulnerabilities in web applications.
                    - **Manual Testing:** Allows for manual testing of security vulnerabilities.
                    - **Passive Scanning:** Passively scans traffic passing through the proxy.
                    - **Spidering:** Crawls the target website to map out the structure and discover hidden files and folders.
                    - **Active Scanning:** Actively probes the target website for vulnerabilities.
                    - **AJAX Spider:** Specifically designed to crawl AJAX-heavy applications.
                - **Quickstart:** [OWASP ZAP Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/owasp_zap_quickstart.md)
        - [ ] **Dependency Scanning:** Checking third-party libraries and dependencies for known vulnerabilities.
            - [ ] **[Snyk](https://docs.snyk.io/scan-using-snyk/supported-languages-and-frameworks/python)**
            - [ ] **[Safety](https://pypi.org/project/safety/)**
            - [ ] **[Bandit](https://pypi.org/project/bandit/)**
            - **Sumary:**
                - `Snyk`, similar to `bandit` and `safety`, is designed to enhance the security of your code, but it offers a broader scope of features. Unlike `bandit`, which focuses on scanning your own code for known vulnerabilities, `Snyk` also checks the libraries your project depends on, much like `safety`. However, `Snyk` goes a step further by integrating directly into your development workflow, offering real-time alerts and automated fix suggestions for vulnerabilities. This makes it particularly effective in not only identifying security issues but also in helping resolve them efficiently. While it shares some functionalities with `safety` in terms of library scanning, its comprehensive approach and developer-friendly tools provide a more robust solution for continuous security monitoring and vulnerability management.
            - **Quickstart:** [Snyk, Safty and Banit Quickstart](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/quickstarts/dependency_scanning_quickstart.md)
- **Security Test Cases and Standards Compliance:**
    - [ ] **API Security Testing:**
        - Testing for common vulnerabilities like SQL injection, Cross-Site Scripting (XSS), and Cross-Site Request Forgery (CSRF).
        - Ensuring authentication, authorization, and data encryption mechanisms are robust.
        - **20 API Security Tips:**
            - [ ] **Regular Updates**: Keep the API code and external packages up-to-date with patches.
            - [ ] **Strong Authentication**: Use OAuth 2.0 or JWT for authorized access.
            - [ ] **HTTPS Encryption**: Transmit data securely with HTTPS.
            - [ ] **Rate Limiting**: Prevent API abuse with rate limiting.
            - [ ] **Data Encryption**: Encrypt sensitive data in transit and at rest.
            - [ ] **Throttle Login Attempts**: Prevent brute-force attacks.
            - [ ] **Security Headers**: Use CSP and X-XSS-Protection.
            - [ ] **Token Expiration**: Set short-lived access tokens.
            - [ ] **Safe API Documentation**: Avoid revealing sensitive information.
            - [ ] **Disable Default Errors**: Prevent revealing internal details.
            - [ ] **Use CSRF Tokens**: Prevent unauthorized requests.
            - [ ] **Access Control**: Define granular permissions for endpoints.
            - [ ] **Sanitize Input**: Sanitize incoming data.
            - [ ] **Secure Error Messages**: Avoid revealing sensitive information.
            - [ ] **Logging and Auditing**: Maintain comprehensive logs.
            - [ ] **API Versioning**: Gracefully handle changes and backward compatibility.
            - [ ] **CORS Configuration**: Restrict cross-origin requests.
            - [ ] **Secure Data Validation**: Validate input and output data.
            - [ ] **Security Testing**: Regularly assess for vulnerabilities.
            - [ ] **Secure Session Management**: Invalidate sessions securely.
    - [ ] **ML/AI/LLM Model Security:**
        - Assessing the security of data pipelines and model serving infrastructure.
        - Evaluating the resilience of ML models against adversarial attacks.
        - [ ] **Prompt Injection**: 
           - [ ] Educate teams about prompt injection, akin to SQL injection, to prevent manipulation of Language Learning Models (LLMs).
           - [ ] Apply least privilege principles between LLMs and data/functionality.
           - [ ] Limit sensitive data access by LLMs.
           - [ ] Sanitize LLM actions and responses.
           - [ ] Use function calling to avoid unstructured data issues.
           - Be cautious of indirect prompt injections.
        - [ ] **Restrict Data Access for LLMs and Sensitive Information Disclosure**: 
           - [ ] Treat LLMs like user data, ensuring careful direct access.
           - [ ] Implement input and output guard checks to sanitize interactions.
           - [ ] Limit the data provided to LLMs.
        - [ ] **Keep a Human in the Loop**: 
           - [ ] Exercise caution with AI-generated code and autonomous agents.
           - [ ] Validate and integrate code security into the development process.
        - [ ] **Secure Your Vulnerabilities**: 
           - [ ] Treat AI-generated code with scrutiny and use tools to automate testing.
           - [ ] Manually verify open-source libraries suggested by AI.
        - [ ] **Don’t Provide IP/Private Info to Public GPT Engines**: 
           - [ ] Avoid sharing sensitive information with public AI engines.
           - [ ] Investigate enterprise-ready versions of AI tools and educate teams on policy.
        - [ ] **Use Hybrid AI Models**: 
           - [ ] Choose the right tool for the job, considering both symbolic AI and LLMs.
           - [ ] Symbolic AI excels in small domains with specific rules, while LLMs are better for broad, general-purpose problems.
        - [ ] **Use Good Training Data**: 
           - [ ] Utilize various in-context learning techniques for LLMs.
           - [ ] Validate data sources and be cautious of data hallucinations.
        - [ ] **Beware of Hallucinations and Misleading Data**: 
           - [ ] Always validate LLM output and be wary of executing dangerous functions without validation.
           - [ ] Consider human interaction to avoid critical data/system impact.
        - [ ] **Keep Track of Your AI Supply Chain**: 
           - [ ] Maintain a list of data sources for training/tuning LLMs.
           - [ ] Validate data using attestation/signing techniques.
           - [ ] Use attestation/signing techniques for data validation 
           - [ ] Evaluate security risks of malicious and typosquatting libraries related to AI and LLMs.
           - [ ] Be cautious of AI-recommended tools or SDKs.
        - [ ] **Insecure Output Handling**:
           - [ ] Prevent direct access of LLMs to sensitive data.
           - [ ] Implement least privilege rules.
           - [ ] Restrict LLMs from executing dangerous functions without validation.
        - [ ] **Training Data Poisoning**:
           - [ ] Validate and verify data sources.
           - [ ] Sandbox data sources to prevent easy external additions.
           - [ ] Sign or attest data used for training.
        - [ ] **Model Denial of Service (MDoS)**:
           - [ ] Restrict input evaluation steps using frameworks like LangChain.
           - [ ] Follow LLM architecture best practices, including circuit breakers.
           - [ ] Sanitize and validate inputs and rate-limit calls.
        - [ ] **Insecure Plugin Design**:
           - [ ] Treat LLM output like user input.
           - [ ] Use varied parameter inputs for plugins.
           - [ ] Consider plugin interactions as API contracts and follow OWASP API Security Risks best practices.
        - [ ] **Excessive Agency**:
           - Avoid excessive:
               - [ ] Functionality
               - [ ] Permissions
               - [ ] Autonomy in LLM applications and plugins.
        - [ ] **Overreliance**:
           - [ ] Treat generated code as if it were written by a junior developer: validate, test, correct.
           - [ ] Use tools for automating AI-generated code security testing.
           - [ ] Educate teams about hallucinations and disinformation from generative AI.
        - [ ] **Model Theft**:
           - [ ] Protect digital IP from unauthorized access to LLMs.
           - [ ] Employ best practices like Role-Based Access Control (RBAC).
    - **Compliance with Security Standards:**
        - Ensuring adherence to relevant security standards such as:
            - [ ] OWASP Top 10
            - [ ] ISO/IEC 27001
            - [ ] Industry-specific regulations:
                - [ ] list regulations [...]

| Security Test Case       | Description             | Methodology        | Compliance Check      | Results              |
|--------------------------|-------------------------|--------------------|-----------------------|----------------------|
| ...                      | ...                     | ...                | ...                   | ...                  |

- [ ] **Results and Mitigation:**
    - **Findings:**
    - Documenting the security vulnerabilities found during testing, categorized by severity.
    - **Mitigation Strategies:**
    - Outlining recommended measures to address identified vulnerabilities.
    - Including timelines and responsibilities for implementing these measures.
- **Security Testing Tools Used:**
    - [List of security testing tools used, such as OWASP ZAP, SonarQube, Fortify, etc.]

### Next Steps:
- Outline of actions following the functional testing phase (e.g., addressing any outstanding issues per section).
- Recommendations for ongoing security monitoring and updates.

### Report Approval:
- **Lead Developer:**
    - **Name:** {{lead_developer_name}}
    - **Title:** {{lead_developer_title}}
    - **Date:** {{ now() }}
    - **Signature:** _________________________
- **QA Lead:**
    - **Name:** {{qa_lead_name}}
    - **Title:** {{qa_lead_title}}
    - **Date:** {{ now() }}
    - **Signature:** _________________________
- **Security Lead:**
    - **Name:** {{security_lead_name}}
    - **Title:** {{security_lead_title}}
    - **Date:** {{ now() }}
    - **Signature:** _________________________
- **Project Manager:**
    - **Name:** {{project_manager_name}}
    - **Title:** {{project_manager_title}}
    - **Date:** {{ now() }}
    - **Signature:** _________________________
- **Client Representative:**
    - **Name:** {{client_representative_name}}
    - **Title:** {{client_representative_title}}
    - **Date:** {{ now() }}
    - **Signature:** _________________________
