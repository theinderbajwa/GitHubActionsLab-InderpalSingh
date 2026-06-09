# GitHub Actions - Automated Workflows Lab

## Purpose of Each Workflow
1. **Dependent Jobs Workflow (dependent-jobs.yml)**: This workflow handles automated tasks that must run in a specific sequence. It uses the `needs` configuration to make sure that the `test` phase only starts after the `build` phase finishes successfully, and the `deploy` phase only starts after the `test` phase passes.
2. **Multi-Platform Testing Workflow (multi-platform.yml)**: This workflow handles automated environment matrix testing. It triggers automatically whenever a new pull request is opened, running identical checkouts and verification jobs across three different operating systems (Linux, Windows, and macOS) at the exact same time.

## Key Concepts Demonstrated
* **needs**: Used to link different jobs together sequentially. This sets up dependencies, forcing a job to wait for another specific job to finish completely before it can begin executing.
* **runs-on**: Configures the underlying operating system environment and operating system architecture (like `ubuntu-latest`, `windows-latest`, or `macos-latest`) provided by GitHub's hosted virtual runners to execute the steps inside a job.
* **env**: Used to declare workflow-level or job-level configuration variables to keep scripts modular, clean, and reusable without hardcoding text values.
