# Dependency Scanning:** Checking third-party libraries and dependencies for known vulnerabilities.
## Sumary
`Snyk`, similar to `bandit` and `safety`, is designed to enhance the security of your code, but it offers a broader scope of features. Unlike `bandit`, which focuses on scanning your own code for known vulnerabilities, `Snyk` also checks the libraries your project depends on, much like `safety`. However, `Snyk` goes a step further by integrating directly into your development workflow, offering real-time alerts and automated fix suggestions for vulnerabilities. This makes it particularly effective in not only identifying security issues but also in helping resolve them efficiently. While it shares some functionalities with `safety` in terms of library scanning, its comprehensive approach and developer-friendly tools provide a more robust solution for continuous security monitoring and vulnerability management.

## [Snyk](https://docs.snyk.io/scan-using-snyk/supported-languages-and-frameworks/python)
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

## [Safety](https://pypi.org/project/safety/)
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

## [Bandit](https://pypi.org/project/bandit/)
```bash
bandit -r path/to/your/code/
```