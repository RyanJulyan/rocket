
### DevSec Ops
#### Process and Controls
1. Plan and Develop
    - [ ] Threat modelling
    - [ ] IDE Security plugins
    - [ ] Pre-commit hooks
    - [ ] Secure coding standards
    - [ ] Peer review
1. Commit the Code
    - [ ] Static Application Security Testing
    - [ ] Security Unit and Functional Tests
    - [ ] Dependency Management 
    - [ ] Secure Pipelines
1. Biuld and Test
    - [ ] Dynamic application security testing
    - [ ] Cloud configuration validation
    - [ ] Infrastructure scanning
    - [ ] Security acceptance testing
1. Go to Production
    - [ ] Security smoke tests
    - [ ] Configuration checks
    - [ ] Live Site Penetration testing
1. Operate
    - [ ] Continuous monitoring
    - [ ] Threat intelligence
    - [ ] Penetration testing
    - [ ] Blameless postmortems

### CI/CD
>The following sequence serves as a guideline for setting up a CI/CD pipeline. This should be treated as a checklist to ensure that all necessary steps have been considered. The sequence can be customized per project, but if followed in the order below, it will provide a solid foundation:

**Automation tool of choice:** {{automation_tool_of_choice}}

#### Local and Pre-Commit
While many of these can happen in the local development environment such as in an IDE, ensuring these are enforced through the pre-commit can prevent issues. Consider including and asking the client about the following:
- [ ] Pre-commit
- [ ] Lint & Formatting
- [ ] Local Package/Module Validation Testing (*required stopping point)
- [ ] Local Static Code Analysis (potential stopping point)
- [ ] Local Static Code Complexity Analysis (potential stopping point)
- [ ] Local Tests (potential stopping point)
- [ ] Local Env Build
- [ ] Local Build Port Scan (if implemented stopping point)
- [ ] Local Versioning

#### Automation & Repo (Git)
Ensure that you are using some sort of `Automation` within the pipeline. Consider including and asking the client about the following:
- [ ] Auto Version
- [ ] Static Code Analysis (potential stopping point)
- [ ] "Test" Build
- [ ] Unit Testing (potential stopping point)
- [ ] Test Code Coverage (potential stopping point)
- [ ] Git Tag
- [ ] "Prod" Build (same build can be used for dev, test and prod, depends on requirements and project, so you may need more or less builds)
- [ ] Port Scan (potential stopping point)
- [ ] Security Module Testing (potential stopping point)
- [ ] Deploy Dev
- [ ] Stub Testing (potential stopping point)
- [ ] Scenario Testing (potential stopping point)
- [ ] Deploy Test
- [ ] Integration Test (potential stopping point)
- [ ] Deploy Prod

#### Post Deploy & Errors
Just having a pipeline is not enough, there are some considerations/steps after the pipeline automation has completed. Consider including and asking the client about the following:
- [ ] Notifications
    - [ ] Internal
    - [ ] Clients
    - [ ] Users
- [ ] Reports
    - [ ] Deployment Error Stages
    - [ ] Test Code Coverage
- [ ] Monitoring

#### Potential other testing
These may be included in the pipeline, however they may also be separate for cost, repeatability, scalability, ability to automate the steps or process. Consider including and asking the client about the following:
- [ ] Performance Testing
- [ ] Regression Testing
- [ ] Penetration Testing
- [ ] Vulnerability Testing
- [ ] Performance Testing
