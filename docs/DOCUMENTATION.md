# Test Framework Documentation

## Overview

This document describes the structure, architecture, and design patterns of our WebDriverIO-based test framework. The framework is designed to support automated end-to-end testing of web applications with a focus on maintainability, reusability, and ease of use.

## Framework Structure

### Directory Structure

- **`test/`**: Contains all test files and test data.
- **`test/specs/`**: Contains all the test suites and test files for different features or components.
- **`test/data/`**: Contains all test data.
- **`pages/`**: Contains Page Object Models for each page of the application.
- **`docs/`**: Contains extensive documentation of the framework.
- **`allure-report/`**: Destination for test execution reports.
- **`allure-results/`**: Contains the raw data for the test execution reports.
- **`wdio.conf.js`**: The main configuration file for WebDriverIO.
- **`package.json`**: Contains all the dependencies and scripts for the project.
- **`README.md`**: Contains instructions for setting up and running the framework.
- **`.gitignore`**: Contains the files and directories that should be ignored by Git.
- **`.github/workflows/`**: Contains the GitHub Actions workflow file for CI.

### Key Files and Their Purpose

- **`wdio.conf.js`**: Configures WebDriverIO with the desired capabilities, test runner, reporters, and hooks.
- **`config.js`**: Contains environment-specific settings and global configurations.
- **`testData.js`**: Houses the data needed for tests, such as user credentials and product information.

## Test Architecture

### Test Suites and Specifications

- Tests are organized into suites by feature or component, with each suite containing multiple test specifications.
- Each test file (`*.test.js`) corresponds to a feature or component of the application.

### PageObject Pattern

- **Purpose**: Encapsulates the structure and behaviors of pages/components in the application, promoting reusability and reducing duplication.
- **Implementation**: Each page or significant component has a corresponding PageObject in the `/pages` directory.

### Data-Driven Tests

- Test data is separated from test logic, allowing for easy updates and scalability.
- `testData.js` provides a centralized location for managing test data.

## Design Patterns

### PageObject Pattern

- **Usage**: Abstracts the UI details from the test logic. Each PageObject provides methods for interacting with a page, hiding the specifics of the UI structure and Selenium calls.
- **Benefit**: Reduces duplication and eases maintenance. Changes in the UI only require updates in one place.

## Reporting

- **Tools**: Configured with Allure to generate detailed and readable reports in the browser.
- **Integration**: Reports are generated after each test run, providing insights into passed, failed, and skipped tests.

## Continuous Integration

- **CI Server**: Integrated with GitHub Actions.
- **Pipeline**: The CI pipeline is configured to check out the code, run tests, and generate reports on every push or pull request.
- **Artifacts**: The pipeline is configured to store the test execution reports as artifacts. To view the artifacts, click on the "Actions" tab in the repository and select the latest workflow run. Download the allure-artifacts zip file and extract it. To view the report, navigate to the extracted `allure-artifacts` directory and run the command `allure open allure-report`.

## Conclusion

This document provides an overview of the test framework's structure, architecture, and design patterns. It's designed to be a living document, evolving as the framework and application under test evolve. For detailed instructions on writing tests, adding PageObjects, or modifying configurations, refer to the specific guide or to README files in the respective directory.
