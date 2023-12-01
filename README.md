# Test Studio Runtime
[![CI](https://github.com/jonathanread/test-studio/actions/workflows/blank.yml/badge.svg)](https://github.com/jonathanread/test-studio/actions/workflows/blank.yml)
This project has a Test Studio project with 2 web tests, one that should succeed and one that should fail. This setup was based on the documentation for [Azure DevOps](https://docs.telerik.com/teststudio/advanced-topics/build-server/microsoft-hosted-agent-testing).
## Steps in the workflow
Test Studio requires a windows based runner.
### Get Test Studio Runtime
We will need to host the Test Studio runtime somewhere accessible so we can get using the workflow and powershell. In this example the runtime is storef on Google Drive. The Test Studio runtime is available via the [Telerik.com Portal](https://www.telerik.com/account/](https://docs.telerik.com/teststudio/prerequisites/installation/run-time-install). Once we have downloaded from Telerik Account we move it to Google Drive. 
### Install Test Studio Runtime
This step installs the Test Studio run and has logging steps that can be turned for debugging purposes.
### Run Test List
We will use the Test Studio Runtime to execute a test list. [Documentation](https://docs.telerik.com/teststudio/features/test-runners/artoftest-runner)
### Publish Test Results
We use a GitHub plugin to publish test results to the build summary.

