# CI/CD Pipeline Test Web Application - Java Spring Boot

This repository houses the "Hello World" web application, a simple project used to test CI/CD pipelines. The application can be built manually using JDK 17 and the Gradle wrapper included, but this repository is intended for use as an SCM (Source Control Management) source for a CI/CD pipeline. This project was bootstrapped with [Spring Initializr](https://start.spring.io/), utilizing Gradle as the build tool and Java 17 for the SDK.

## Project Setup

### Prerequisites

Ensure you have the following installed:

- JDK 17
- An account on a CI/CD platform (e.g., Jenkins, Travis CI, GitHub Actions)

### Local Setup

To set up the project locally:

1. Clone the repository:
```
git clone https://github.com/nld91/ci-cd-test-webapp-java-springboot.git
```

2. Navigate into the project directory:
```
cd ci-cd-test-webapp-java-springboot
```

3. Build the project using the Gradle wrapper to ensure all dependencies are correctly downloaded:
```
./gradlew build
```

4. Optionally, run the application locally to verify it's working:
```
./gradlew bootRun
```
The application will start and be accessible at `http://localhost:9090`, displaying "Hello World!" when visited with a web browser. Port binding can be altered in `src/main/resources/application.properties`

## Integrating with CI/CD

### Creating a Pipeline

1. **Jenkins:**
   - Create a new "Pipeline" job.
   - Use this repository as the SCM source.
   - Define the pipeline script to automate the build, test, and deployment stages. You can use the Jenkinsfile provided in this repository or create your own.

2. **GitHub Actions:**
   - Navigate to your repository on GitHub.
   - Go to the "Actions" tab and set up a new workflow.
   - Use the provided `.github/workflows/main.yml` as a starting point to build, test, and deploy your application.

3. **Travis CI:**
   - Sign in to Travis CI with your GitHub account and enable this repository for testing.
   - Add a `.travis.yml` file to define the build and test process.

### Pipeline Stages

Your CI/CD pipeline should include the following stages:

- **Build:** Compile the application and create an executable jar.
- **Test:** Run automated tests to verify the application behaves as expected.
- **Deploy:** Push the built application to a staging or production environment.

Example `Jenkinsfile`:

```
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
        stage('Deploy') {
            steps {
                // Add your deployment steps here
            }
        }
    }
}
```

## Deployment

Your deployment steps will vary based on your specific hosting environment (AWS, Azure, GCP, etc.). Generally, you will:

- Package the application into a Docker container.
- Push the container to a container registry.
- Deploy the container to your host.

See the hosting provider's documentation for specific deployment instructions.

## Contributing

Thank you for your interest in contributing! As the sole maintainer of this project, I am always looking for ways to improve it and I warmly welcome any contributions you might have. Whether it's suggesting new features, reporting bugs, or even submitting pull requests with fixes or enhancements, your input is highly valued.

Here's how you can contribute:

1. **Report Issues**: If you encounter any bugs or would like to suggest a new feature or enhancement, please use the [Issues](https://github.com/nld91/ci-cd-test-webapp-java-springboot/issues) section of this GitHub repository. Provide as much detail as you can to help understand the context and potential impact.

2. **Submit Pull Requests**: If you're able to contribute code, documentation updates, or other resources to the project, please do so by submitting a pull request. Here's a brief guide on how to do it:
   - Fork the repository.
   - Create a new branch in your forked repository for your changes.
   - Make your changes in the branch.
   - Commit your changes with clear and concise commit messages.
   - Push the changes to your fork.
   - Submit a pull request to the main repository from your branch. Include a detailed description of your changes and the reason for them.

3. **Review Open Pull Requests**: If you're interested and have the expertise, reviewing open pull requests is a great way to contribute. Your feedback can help improve the quality of submissions and foster a collaborative environment.

4. **Spread the Word**: If you find this project useful, consider sharing it with others who might benefit from it. Word of mouth is a powerful tool for open-source projects to gain visibility and support.

As an individual developer, your support and contributions make a significant difference. They not only help improve the project but also foster a community of collaboration and innovation. I look forward to seeing your contributions and working together to make this project even better!

Thank you for your support!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Java Spring Boot "Spring Initializr": https://github.com/spring-io/start.spring.io