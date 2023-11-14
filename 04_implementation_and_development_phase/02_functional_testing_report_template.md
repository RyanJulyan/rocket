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

### Functional Testing Overview:
- **Purpose:** [State the objectives of functional testing]
- **Scope:** [Define the scope of testing, including which features and components will be tested]

### Unit Testing:
- **Methodology:**
    - **Framework:** Utilize Python's `pytest` framework for writing and executing unit tests.
    - **Test Driven Development (TDD):** Follow TDD practices where tests are written prior to writing the actual code.
    - **Isolation:** Ensure unit tests are isolated, testing one component at a time.
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
- **Performance Benchmarks:**
   - Establish benchmarks for response times, throughput, and error rates.
   - Use profiling tools like [scalene](https://github.com/plasma-umass/scalene) to identify bottlenecks in the code.
- **Performance Metrics:**
    - Specific performance metrics that were tested:
        - Response time under load
        - Concurrency
        - System stability
- **Results & Optimization:**
    - Analyze test results to identify areas for performance optimization.
    - Implement caching, query optimization, or other techniques to improve performance.

### Next Steps:
- Outline of actions following the functional testing phase (e.g., addressing any outstanding issues).

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
