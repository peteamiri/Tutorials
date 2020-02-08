# DevSecOps

* [Code Scanning Tools](https://owasp.org/www-community/Source_Code_Analysis_Tools)
* [Process](https://stackify.com/devsecops-automate-security-testing/)
* [Good Resource](https://opensource.com/article/19/4/devops-pipeline)

### Understanding the DevSecOps pipeline
There are different stages in a typical DevOps pipeline; a typical SDLC process includes phases like Plan, Code, Build, Test, Release, and Deploy. In DevSecOps, specific security checks are applied in each phase.

* `Plan`: Execute security analysis and create a test plan to determine scenarios for where, how, and when testing will be done.

* `Code`: Deploy linting tools and Git controls to secure passwords and API keys.

* `Build`: While building code for execution, incorporate static application security testing (SAST) tools to track down flaws in code before deploying to production. These tools are specific to programming languages.

* `Test`: Use dynamic application security testing (DAST) tools to test your application while in runtime. These tools can detect errors associated with user authentication, authorization, SQL injection, and API-related endpoints.

* `Release`: Just before releasing the application, employ security analysis tools to perform thorough penetration testing and vulnerability scanning.

* `Deploy`: After completing the above tests in runtime, send a secure build to production for final deployment.
