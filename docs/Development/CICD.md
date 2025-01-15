# Workflow 1: Build and Test on Push or Pull Request

This workflow automates building and testing a project when code is pushed or a pull request is created for the main branch.
## Trigger
- **Push**: Activated on any push to the main branch.
- **Pull Request**: Activated for pull requests targeting the main branch.

### Jobs
- Runs on: ubuntu-latest
- Steps:
    - Checkout Code:
        - **Action**: actions/checkout@v2
        - **Purpose**: Clones the repository to the runner for building and testing.
    - Set up JDK 17:
        - **Action**: actions/setup-java@v1
        - **Purpose**: Sets up Java Development Kit (JDK) version 17 for Gradle-based projects.
        - Parameters:
            - **java-version**: '17'
        - Build with Gradle:
            - **Command**: ./gradlew build
            - **Purpose**: Builds the project using Gradle.
        - Run Tests:
            - **Command**: ./gradlew test
            - **Purpose**: Executes tests to ensure code quality and functionality.

# Workflow 2: Auto-Label Issues

This workflow automatically applies appropriate labels to newly opened issues based on their content.
## Trigger
- **Issues**: Activated when a new issue is opened.

### Jobs
- Runs on: ubuntu-latest
- Steps:
    - Checkout Sparse Workflow Configuration:
        - **Action**: actions/checkout@v4
        - **Purpose**: Checks out the repository, specifically the .github/workflows/auto-label.json5 file.
        - Parameters:
            - **sparse-checkout**: Specifies the file or directory to checkout.
            - **sparse-checkout-cone-mode**: false: Ensures a specific file or directory is targeted.
        - Run Auto-Label Action:
            - **Action**: Renato66/auto-label@v3
            - **Purpose**: Automatically labels issues based on defined rules.
            - Parameters:
                - **repo-token**: Token for authenticating with the repository.

##  Label Configuration
- Labels Synonyms:
    - Defines synonyms for mapping terms in issue titles or descriptions to specific labels.
    - Example: bug is mapped to terms like error, need fix, not working.
- Labels Not Allowed:
    - Prevents certain labels from being applied. Example: duplicate, good first issue.
- Default Labels:
    - Adds a default label (TODO) to all issues.
- Ignore Comments:
    - Ensures that comments in issues are not considered for labeling.

## Example Use Case

If an issue contains the word upgrade, it will automatically be labeled as enhancement.


# Workflow 3: iOS Build and TestFlight Deployment

This workflow automates building and deploying an iOS app to TestFlight using Xcode Cloud when a new tag is created in the GitHub repository.
## Trigger
- Tag: Activated when a new tag is pushed to the repository.

### Jobs
- Runs on: macos-latest
- Steps:
    - Checkout Code:
        - Uses a GitHub Action to clone the repository for building the iOS app.
    - Set Up Xcode Environment:
        - Configures the environment with the required Xcode version for the build process.
    - Install Dependencies:
        - Installs necessary project dependencies (e.g., CocoaPods) if applicable.
    - Build and Archive the iOS App:
        - Builds the iOS app and generates an archive file suitable for TestFlight deployment.
    - Export the Archive for App Store:
        - Prepares the archive for upload using an export options file configured for TestFlight distribution.
    - Upload to TestFlight:
        - Uploads the exported build to TestFlight using credentials for App Store Connect.

