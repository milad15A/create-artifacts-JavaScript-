# Creating Artifacts in a JavaScript Project

This repository demonstrates how to build a multi-job GitHub Actions workflow for a JavaScript application that:

* Runs tests
* Builds executables
* Uses artifacts to pass files between jobs
* Uses the Bun JavaScript runtime through an action from GitHub Marketplace
* This is part of a challenge to build a workflow that creates, uploads, and downloads artifacts.

#  What This Workflow Does

This workflow contains three jobs, executed in strict order:

✔ 1. Test Job

* Installs Bun runtime
* Runs the JavaScript test suite
* Saves the test report as an artifact

✔ 2. Build Job

* Runs only after the Test Job
* Builds platform executables using Bun
* Uploads all executables as artifacts

✔ 3. Linux Executable Test Job

* Runs after the Build Job
* Downloads the Linux executable
* Runs automated tests against the compiled binary
* Saves the test report as an artifact
