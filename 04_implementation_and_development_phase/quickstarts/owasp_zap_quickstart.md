# Quickstart with OWASP ZAP:
1. Download and install OWASP ZAP from the [official website](https://www.zaproxy.org/download/).
1. Open ZAP. The tool may ask if you want to persist the session. Choose as per your requirement.
1. To set up a proxy, go to 'Tools' > 'Options' > 'Local Proxy' and configure your local proxy settings.
1. Configure your browser to use the ZAP Proxy. You can do this manually or use ZAP's option to generate a Root CA certificate for SSL support.
1. Start your browser and navigate to the website you wish to test. ZAP will start capturing traffic between your browser and the target website.
1. Use the ‘Spider’ feature to automatically crawl the website and identify URLs.
1. Utilize the ‘Active Scan’ feature to perform an active scan on the crawled URLs for vulnerabilities.
1. Analyze the results in ZAP's interface, where you will find detailed information about each vulnerability detected.