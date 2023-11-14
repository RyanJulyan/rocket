# Functional Testing Report Template

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
| {{client_security_testing_and_standards_name}}                                   | {{client_security_testing_and_standards_role}}                                   | Security Testing and Standards                                       |

### Functional Testing Overview:
- **Purpose:** [State the objectives of functional testing]
- **Scope:** [Define the scope of testing, including which features and components will be tested]

### Unit Testing:
- **Methodology:**
    - **Framework:** Utilize Python's `pytest` framework for writing and executing unit tests.
    - **Test Driven Development (TDD):** Follow TDD practices where tests are written prior to writing the actual code.
    - **Isolation:** Ensure unit tests are isolated, testing one component at a time.
- **Standards:**
    - Structure of a Unit Test
    - Unit tests generally follow the "Three A's" pattern: Arrange, Act, and Assert, with the addition of mocks before the "Arrange" phase. For more details on "The Three A's", you can refer to [The Three A's of Unit Testing](https://dev.to/coderjay06/the-three-a-s-of-unit-testing-b22).
        - **Fixtures**: Use fixtures to set up any preconditions for your test, like database connections or configuration settings.
        - **Mocks**: Use mocks to isolate the unit of work from external dependencies or services.
        - **Arrange**: Set up the objects and variables to be tested.
        - **Act**: Perform the action that you want to test.
        - **Assert**: Check that the action has the expected outcome.
    - **Quickstart Example:**
        - To install pytest, run:
        ```bash
        pip install pytest
        ```
        - An example function:
        ```python
        # fetch_data.py

        # Your function that fetches data from an external API
        def fetch_data(api_url):
            # some code that fetches data
            pass

        ```
        - A simple test case using pytest could look like this:
        ```python
        # test_fetch_data.py
        from unittest.mock import patch
        import pytest

        from fetch_data import fetch_data

        # Fixtures
        @pytest.fixture
        def mock_data():
            return {'key': 'value'}

        # Your test case
        def test_fetch_data_given_mocked_api_expect_correct_data_returned(mock_data):
            # Mocks & Arrange
            with patch('your_module_name.fetch_data') as mock_fetch:
                mock_fetch.return_value = mock_data

                # Act
                result = fetch_data('some_api_url')

                # Assert
                assert result == mock_data


        ```
        - In this example, the test function is now named `test_fetch_data_given_mocked_api_expect_correct_data_returned`, which clearly describes what the test is doing:
            - Testing the `fetch_data` function
            - Given a mocked API
            - Expects to get the correct data returned
            - This makes it easier to understand the purpose of the test, especially when you have a large number of tests.
        - To run the test, execute:
        ```bash
        pytest test_fetch_data.py
        ```
    - **External `pytest` Examples**: [Real Python's Guide on Python Testing with Pytest](https://realpython.com/python-testing/)
- **Test Cases and Coverage:**
    - **API Endpoint Testing:** Write test cases for each API endpoint, testing for expected responses, error handling, and edge cases.
    - **ML Model Testing:** Test machine learning models for accuracy, overfitting, and underfitting. Use libraries like `scikit-learn` for model testing.
    - **AI Algorithm Testing:** Test AI algorithms for correctness, efficiency, and expected behavior under various scenarios.

| Test Case Name | conditions       | Assertions       | Mocks            | Coverage Metrics |
|----------------|------------------|------------------|------------------|------------------|
| ...            | ...              | ...              | ...              | ...              |

- **Results:**
    - Utilize Continuous Integration (CI) tools to automatically run unit tests and report results.
    - Monitor for high pass rates and address any failing tests promptly.
- **Issues and Resolutions:**
    - Document any issues encountered during testing, including bugs in logic, performance issues, or integration problems, and track their resolution.

### User Acceptance Testing (UAT):
- **UAT Plan:**
    - **Objectives:** Define clear objectives focusing on end-user requirements and the usability of the API, ML, and AI components.
    - **Success Criteria:** Establish criteria for successful UAT, such as specific user tasks being completed efficiently.
- **UAT Procedures:**
    - **Participant Selection:** Choose a diverse group of users, representative of the end-users.
    - **Feedback Mechanism:** Implement a structured feedback mechanism to gather detailed user responses.
- **User Testing Sessions:**
    - Schedule planning sessions and get some key users invloved in the structure and examples of user testing sessions.
        - Try allow them to run and explain some of the application
    - Conduct structured sessions where users interact with the system, focusing on real-world use cases.
- **Feedback & Iterations:**
    - Analyze feedback for trends and common issues.
    - Iterate on the API, ML models, and AI algorithms based on this feedback.
    - Use the [Change Request Template](https://github.com/RyanJulyan/rocket/blob/main/04_implementation_and_development_phase/03_change_request_template.md) to manage these changes

### Load Testing:
- **Load Testing Strategy:**
    - **Tools:** Utilize `JMeter` for simulating user traffic to the API.
    - **Scenarios:** Design scenarios that mimic real-world usage, including high traffic and peak usage times.
        - Use `JMeter`'s CSV functionality to ensure that the tests are repeatable and scalable
            - **JMeter Quickstart:**
                - **Step 1: Installation:**
                    1. **Download JMeter**: Visit the [Apache JMeter website](https://jmeter.apache.org/) and download the latest version of JMeter.
                    1. **Install Java Development Kit (JDK)**: Ensure you have a JDK installed on your machine as JMeter is a Java application. You can download an open-source distribution of OpenJDK, verified by TCK for Java SE. Liberica JDK binaries from the [BellSoft Liberica JDK website](https://bell-sw.com/pages/downloads/).
                    1. **Unzip and Launch**: Unzip the JMeter download and navigate to the `bin` directory. Run `jmeter.bat` for Windows or `jmeter.sh` for Unix/Linux to start JMeter.
                - **Step 2: Creating Your First Test Plan:**
                    1. **Open JMeter**: Launch JMeter to open the GUI.
                    1. **Create a Test Plan**: Click on “Test Plan” and rename it if desired.
                    1. **Add a Thread Group**: Right-click on the Test Plan > Add > Threads (Users) > Thread Group. Here you can set the number of users, ramp-up period, and the number of times to execute the test.
                - **Step 3: Configuring Samplers:**
                    1. **Add Samplers**: Right-click on the Thread Group > Add > Sampler. Select the type of request (e.g., HTTP Request).
                    1. **Configure Sampler**: Enter the details of the web request (e.g., website URL, request method).
                - **Step 4: Adding Listeners:**
                    1. **Add Listeners**: Right-click on the Thread Group > Add > Listener. Listeners help you view the results of test execution in different formats (e.g., Tree, Table, Graph).
                    1. **Configure Listener**: Choose the type of listener and configure it according to your needs.
                - **Step 5: Adding CSV Data Set Config to JMeter**
                    1. Preparing Your CSV File
                        - **Create a CSV File**: Prepare a CSV file with the data you want to use in your test. This could include various parameters like usernames, passwords, search queries, etc. Make sure this file is in a simple format with each column having a unique header.
                            - Example CSV File:
                            ```
                            username,password
                            user1,pass1
                            user2,pass2
                            ...
                            ```
                    1. Adding the CSV Data Set Config
                        1. **Add CSV Data Set Config**: In JMeter, right-click on the Test Plan or Thread Group > Add > Config Element > CSV Data Set Config.
                        1. **Configure CSV Data Set Config**:
                            - **Filename**: Enter the path to your CSV file.
                            - **Variable Names**: Enter the column headers from your CSV file, separated by commas (e.g., `username,password`).
                            - **Delimiter**: Set the delimiter used in your CSV file (typically a comma).
                            - **Other Settings**: Adjust other settings like "Allow quoted data?" or "Recycle on EOF?" according to your needs.
                    1. Configuring the HTTP Request to Use CSV Data
                        - **Add/Edit HTTP Request Sampler**: If you haven't added an HTTP Request sampler yet, add one. If you have, simply edit it.
                        - **Use Variables in Request**: In your HTTP Request, use the variable names from the CSV Data Set Config. For example, if you are testing a login feature, you might use `${username}` and `${password}` in the request parameters or body.
                        - **Example:**
                            - For a POST request, you can use these variables in the request body or parameters section.
                            - If it's a GET request, you might use them as query parameters in the URL.
                - **Step 6: Running the Test:**
                    1. **Save Your Test Plan**: Save your test plan with a .jmx extension.
                    1. **Run the Test**: Click the "Run" menu and select "Start" to begin testing. Monitor the test execution through the configured listeners. JMeter will now read data from your CSV file and use it in the HTTP requests.
            - **Analyzing Results:**
                - After the test run completes, analyze the results in the listeners. Look for response times, error rates, and throughput to understand the performance of your application.
            - **Additional Tips:**
                - **File Path**: Ensure the CSV file path is correct. If JMeter is unable to find the file, it will not run the test.
                - **Variable Scope**: Make sure the CSV Data Set Config is at the correct level in your test plan so that the variables are accessible where needed.
                - **Data Formatting**: Ensure the data in your CSV file is correctly formatted and matches the expected format of your HTTP requests.
                - **Non-GUI Mode**: For larger tests, run JMeter in non-GUI mode for less resource consumption. Use the command line to execute tests.
                - **Plugins**: Consider using plugins for extended functionality.
                - **Documentation and Community**: Refer to the [JMeter User Manual](https://jmeter.apache.org/usermanual/index.html) for detailed guidance, and consider engaging with the JMeter community for support and advanced tips.

- **Performance Benchmarks:**
    - Establish benchmarks for response times, throughput, and error rates.
    - Use profiling tools like to identify bottlenecks in the code:
        - For Project-Level Profiling use: [Scalene](https://github.com/plasma-umass/scalene)
            - **Description**: A high-resolution, low-overhead profiler that measures CPU, GPU, and memory usage.
            - **Scalene Quickstart:**
                - To install Scalene, run:
                ```bash
                pip install scalene
                ```
                - To profile your Python script (`your_script.py`), run:
                ```bash
                scalene your_script.py
                ```
                - This will generate a profile report indicating CPU, GPU, and memory usage.
        - For Function-Level Profiling use: [Python timeit](https://docs.python.org/3/library/timeit.html)
            - **Description**: A Python library for measuring the execution time of small bits of Python code. It has both a Command-Line Interface and a callable one.
            - **timeit Quickstart:**
                - You can use `timeit` in your Python script as follows:
                ```python
                import timeit

                def example_function():
                    return sum(range(100))

                # Measure the execution time of 'example_function'
                execution_time = timeit.timeit("example_function()", globals=globals(), number=1000)
                print(f"Execution time: {execution_time} seconds")
                ```
                - Alternatively, you can use it from the command line:
                ```bash
                python -m timeit -s 'from your_script import example_function' 'example_function()'
                ```
                - This will output the average time taken for executing `example_function()`.
- **Performance Metrics:**
    - Specific performance metrics that were tested:
        - Response time under load
        - Concurrency
        - System stability
- **Results & Optimization:**
    - Analyze test results to identify areas for performance optimization.
    - Implement caching, query optimization, or other techniques to improve performance.

### Security Testing and Standards:
- **Security Testing Methodology, Approach and Phases:**
    - **Planning Phase:** Identifying key assets, defining security requirements, and establishing testing goals.
    - **Threat Modeling:** Creating a threat model to identify potential security threats and vulnerabilities.
    - **Test Planning:** Developing a detailed security testing plan, including tools, techniques, and schedules.
    - **Execution Phase:** Conducting the security tests as per the plan.
    - **Analysis Phase:** Analyzing test results to identify security flaws and vulnerabilities.
    - **Reporting and Feedback:** Documenting findings and providing actionable recommendations.
- **Basic Principles:**
    - Always **prioritize security** in all aspects of development.
    - **Regularly update packages and dependencies.**
    - **Encrypt sensitive data both in transit and at rest.**
    - **Secret Management:**
        - **Python-dotenv;**
            - Use [Python-dotenv](https://pypi.org/project/python-dotenv/) for managing `.env` files.
        - **Secrets Vault:**
            - For storing secrets in a more secure manner, consider using a secrets vault.
        - **Basic Principles:**
            - Never commit secrets to the repository.
            - Use environment-specific configuration files for managing secrets.
        - **Stop Using `.env` Files for _Everything_:**
            - Follow the guidelines from this [dev.to article](https://dev.to/gregorygaines/stop-using-env-files-now-kp0) which suggests not using `.env` files for everything. Instead, `.env` files should only be used for API keys and environment variables for the secrets vault.
    - Follow the **[OWASP Top Ten](https://owasp.org/www-project-top-ten/)** as a foundational framework for security testing. The OWASP Top Ten provides a list of the most critical web application security risks and how to mitigate them.
        - For a practical understanding of penetration testing, consider watching [this YouTube video](https://www.youtube.com/watch?v=YYe0FdfdgDU) which provides a hands-on demonstration.
- **Trusting Your Workspace:**
    - Follow the guidelines from the [VS Code documentation](https://code.visualstudio.com/docs/devcontainers/containers#_trusting-your-workspace) to trust your workspace.
- **Security Testing Strategy:**
    - **Purpose and Scope:**
        - Outlining the specific objectives and scope of security testing, focusing on identifying and mitigating security vulnerabilities within the API, ML, and AI components.
    - **Testing Methods:**
        - **Static Application Security Testing (SAST):** Utilizing tools to analyze source code for potential security vulnerabilities.
            - **Complexity Index:**
                - Use [Flake8](https://pypi.org/project/flake8/) to measure the complexity of the code; aim for a score below 12
            - **Static Code Analysis:**
                - **Local:** Use [MyPy](https://mypy.readthedocs.io/en/stable/getting_started.html) for type checking and static code analysis
                - **CI/CD:** Use [SonarQube](https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/) for type checking and static code analysis in the ID
            - **Linting:**
                - Use [Black](https://pypi.org/project/black/) for code formatting
            - **Type Hinting:**
                - Always use type hints for function arguments and return types at the top level
                - use the standary `typing` library for type hints
        - **Dynamic Application Security Testing (DAST):** Conducting tests on running applications to identify real-time security issues.
            > **_Remember, any penetration testing tool like `Burp Suite` and `OWASP ZAP` are powerful and should be used responsibly and legally. Always have explicit and documented permission to test a website before using a tool like ZAP for security testing._**
            - [Burp Suite Community Edition](https://portswigger.net/burp/communitydownload) is a widely used tool for web security testing. It's popular among penetration testers and ethical hackers for its rich feature set and user-friendly interface.
            - **Key Capabilities of Burp Suite Community Edition:**
                - **Proxy Tool:** Allows interception, inspection, and modification of raw traffic passing between your browser and the web server.
                - **Scanner:** Automated scanner (limited in the Community Edition) to identify vulnerabilities in web applications.
                - **Intruder:** A powerful tool for carrying out customized attacks to find and exploit unusual vulnerabilities.
                - **Repeater:** Modify and resend individual requests, and analyze the responses.
                - **Sequencer:** Analyzes the quality of randomness in an application’s session tokens.
                - **Comparer:** Compares application data like request/response pairs, highlighting the differences.
                - **Extensibility:** Ability to extend functionality using the Burp Extender.
            - **Quickstart with Burp Suite Community Edition:**
                1. Download and install Burp Suite Community Edition from the official website.
                1. Open Burp Suite and start a new project or open an existing one.
                1. Go to the "Proxy" tab and ensure the proxy listener is active. You may adjust the interface and port settings as needed.
                1. Configure your web browser to use Burp as its proxy. This typically involves setting the browser’s proxy server settings to the address and port where Burp’s Proxy listener is running.
                1. Navigate to a website using your browser. Burp Suite will capture the traffic in the Proxy > HTTP History tab.
                1. Use the "Intruder" feature to perform customized attacks or the "Repeater" to manually modify and resend requests.
                1. Examine the responses and analyze them for potential security vulnerabilities.
            - [OWASP ZAP](https://www.zaproxy.org/download/) is a powerful penetration testing tool for finding vulnerabilities in web applications. It is designed to be used by both those new to application security as well as professional penetration testers.
                - **Key Capabilities of OWASP ZAP:**
                    - **Automated Scanner:** Scans for vulnerabilities in web applications.
                    - **Manual Testing:** Allows for manual testing of security vulnerabilities.
                    - **Passive Scanning:** Passively scans traffic passing through the proxy.
                    - **Spidering:** Crawls the target website to map out the structure and discover hidden files and folders.
                    - **Active Scanning:** Actively probes the target website for vulnerabilities.
                    - **AJAX Spider:** Specifically designed to crawl AJAX-heavy applications.
                - **Quickstart with OWASP ZAP:**
                    1. Download and install OWASP ZAP from the [official website](https://www.zaproxy.org/download/).
                    1. Open ZAP. The tool may ask if you want to persist the session. Choose as per your requirement.
                    1. To set up a proxy, go to 'Tools' > 'Options' > 'Local Proxy' and configure your local proxy settings.
                    1. Configure your browser to use the ZAP Proxy. You can do this manually or use ZAP's option to generate a Root CA certificate for SSL support.
                    1. Start your browser and navigate to the website you wish to test. ZAP will start capturing traffic between your browser and the target website.
                    1. Use the ‘Spider’ feature to automatically crawl the website and identify URLs.
                    1. Utilize the ‘Active Scan’ feature to perform an active scan on the crawled URLs for vulnerabilities.
                    1. Analyze the results in ZAP's interface, where you will find detailed information about each vulnerability detected.
        - **Dependency Scanning:** Checking third-party libraries and dependencies for known vulnerabilities.
            - **[Snyk](https://docs.snyk.io/scan-using-snyk/supported-languages-and-frameworks/python)**
                - Prerequisites
                    1. Create a Snyk account.
                    1. Install Snyk CLI and authenticate your machine.
                    1. Set the default Organization for all Snyk tests (code analysis).
                    1. Ensure you have installed the relevant package manager before you begin using the Snyk CLI (open source).
                    1. Ensure you have included the relevant manifest files supported by Snyk before testing.
                ```bash
                snyk auth

                snyk test --all-projects
                ```
            - **[Safety](https://pypi.org/project/safety/)**
                ```bash
                pip install safety
                ```
                ```bash
                safety check
                ```
                - To scan a requirements file:
                ```bash
                safety check -r requirements.txt
                ```
            - **[Bandit](https://pypi.org/project/bandit/)**
                ```bash
                bandit -r path/to/your/code/
                ```
            - **Sumary:**
                - `Snyk`, similar to `bandit` and `safety`, is designed to enhance the security of your code, but it offers a broader scope of features. Unlike `bandit`, which focuses on scanning your own code for known vulnerabilities, `Snyk` also checks the libraries your project depends on, much like `safety`. However, `Snyk` goes a step further by integrating directly into your development workflow, offering real-time alerts and automated fix suggestions for vulnerabilities. This makes it particularly effective in not only identifying security issues but also in helping resolve them efficiently. While it shares some functionalities with `safety` in terms of library scanning, its comprehensive approach and developer-friendly tools provide a more robust solution for continuous security monitoring and vulnerability management.
- **Security Test Cases and Standards Compliance:**
    - **API Security Testing:**
        - Testing for common vulnerabilities like SQL injection, Cross-Site Scripting (XSS), and Cross-Site Request Forgery (CSRF).
        - Ensuring authentication, authorization, and data encryption mechanisms are robust.
        - **20 API Security Tips:**
            1. **Regular Updates**: Keep the API code and external packages up-to-date with patches.
            1. **Strong Authentication**: Use OAuth 2.0 or MT for authorized access.
            1. **HTTPS Encryption**: Transmit data securely with HTTPS.
            1. **Rate Limiting**: Prevent API abuse with rate limiting.
            1. **Data Encryption**: Encrypt sensitive data in transit and at rest.
            1. **Throttle Login Attempts**: Prevent brute-force attacks.
            1. **Security Headers**: Use CSP and X-XSS-Protection.
            1. **Token Expiration**: Set short-lived access tokens.
            1. **Safe API Documentation**: Avoid revealing sensitive information.
            1. **Disable Default Errors**: Prevent revealing internal details.
            1. **Use CSRF Tokens**: Prevent unauthorized requests.
            1. **Access Control**: Define granular permissions for endpoints.
            1. **Sanitize Input**: Sanitize incoming data.
            1. **Secure Error Messages**: Avoid revealing sensitive information.
            1. **Logging and Auditing**: Maintain comprehensive logs.
            1. **API Versioning**: Gracefully handle changes and backward compatibility.
            1. **CORS Configuration**: Restrict cross-origin requests.
            1. **Secure Data Validation**: Validate input and output data.
            1. **Security Testing**: Regularly assess for vulnerabilities.
            1. **Secure Session Management**: Invalidate sessions securely.
    - **ML/AI Model Security:**
        - Assessing the security of data pipelines and model serving infrastructure.
        - Evaluating the resilience of ML models against adversarial attacks.
    - **Compliance with Security Standards:**
        - Ensuring adherence to relevant security standards such as OWASP Top 10, ISO/IEC 27001, and industry-specific regulations.

| Security Test Case       | Description             | Methodology        | Compliance Check      | Results              |
|--------------------------|-------------------------|--------------------|-----------------------|----------------------|
| ...                      | ...                     | ...                | ...                   | ...                  |

- **Results and Mitigation:**
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
