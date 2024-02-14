# Test Studio Runtime
[![CI](https://github.com/jonathanread/test-studio/actions/workflows/blank.yml/badge.svg)](https://github.com/jonathanread/test-studio/actions/workflows/blank.yml)

This project has a Test Studio project with 2 web tests, one that should succeed and one that should fail. This setup was based on the documentation for [Azure DevOps](https://docs.telerik.com/teststudio/advanced-topics/build-server/microsoft-hosted-agent-testing).
## Steps in the workflow
Test Studio requires a windows based runner.
### Get Test Studio Runtime
To run Test Studio tests or test lists we need the [runtime](https://docs.telerik.com/teststudio/test-studio-editions#test-studio-run-time-add-on) We have chosen to use the GitHub [release feature] (https://github.nih.gov/about/features/releases#:~:text=Releases%20allow%20users%20to%20download,are%20dependent%20on%20git%20tags%20) to store the msi and version it for use in our Actions. To get the release asset we are using [release-downloader](https://github.com/marketplace/actions/release-downloader) from the GitHub marketplace. When using the release we chose to make the msi file always name 'Telerik.TestStudio.msi' and use the tags feature to version instances of the runtime.
### Install Test Studio Runtime
This step installs the Test Studio run and has logging steps that can be turned for debugging purposes.
### Run Test List
We will use the Test Studio Runtime to execute a test list. [Documentation](https://docs.telerik.com/teststudio/features/test-runners/artoftest-runner)
### Publish Test Results
We use a GitHub plugin to publish test results to the build summary using [EnricoMi](https://github.com/EnricoMi/publish-unit-test-result-action#running-as-a-composite-action).
