# Maven Template

This project is a template for creating and deploying a Maven package. The package is hosted on GitHub Packages.

## Getting Started

These instructions will help you set up the project on your local machine for development and deployment purposes.

### Prerequisites

Ensure you have the following software installed:

- [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Apache Maven](https://maven.apache.org/download.cgi)
- [Git](https://git-scm.com/)

### Installation

1. **Clone the Repository**

   ```sh
   git clone https://github.com/kavicastelo/maven-template.git
   cd maven-template
   ```

2. **Configure Maven**
   Ensure your `settings.xml` is configured with your GitHub credentials. This file is usually located in the `.m2`
   directory in your home directory.

   ```xml
   <settings>
     <servers>
       <server>
         <id>github</id>
         <username>your_github_username</username>
         <password>your_github_password</password>
       </server>
     </servers>
   </settings>
   ```

3. **Build the Package**
   Run the following command to build the project:

   ```sh
   mvn clean install
   ```

### Deployment

To deploy the package to GitHub Packages, run:

```sh
mvn clean deploy
```

### Distribution Management

Ensure your `pom.xml` includes the correct `distributionManagement` section:

```xml

<distributionManagement>
    <snapshotRepository>
        <id>github</id>
        <url>https://maven.pkg.github.com/kavicastelo/maven-template</url>
    </snapshotRepository>
    <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/kavicastelo/maven-template</url>
    </repository>
</distributionManagement>
```

### Using the Package

To use this package in your own Maven project, add the following to your `pom.xml`:

1. Repository Configuration

   ```xml
   <repositories>
      <repository>
         <id>github</id>
         <url>https://maven.pkg.github.com/kavicastelo/maven-template</url>
      </repository>
   </repositories>
   ```

2. Dependency Declaration

   ```xml
   <dependencies>
      <dependency>
         <groupId>com.example</groupId>
         <artifactId>maven-template</artifactId>
         <version>1.0-SNAPSHOT</version>
      </dependency>
   </dependencies>
   ```

### Contributing

1. Fork the repository.
2. Create your feature branch: `git checkout -b feature/my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin feature/my-new-feature`
5. Submit a pull request.

### License
This project is licensed under the Apache License, Version 2.0. See the [LICENSE](#LICENSE) file for details.

### Acknowledgements
- [GitHub Packages Documentation](https://docs.github.com/en/packages)
- [Maven Documentation](https://maven.apache.org/guides/index.html)
