
## Simple Demo web app for XL Deploy to be used with Jenkins to run the CI pipeline.

In dar/pom.xml set the application name and the package version:
```
    <applicationName>PetPortal</applicationName>
    <packageVersion>1.0</packageVersion>
```

Run the following commands to deploy the dar file in your XL Deploy server:
```
mvn clean package
cd dar
mvn xldeploy:import
```

To create a default infrastructure and environment use the yaml files.
Run the following commands:
```
cd yaml
xl apply --xl-deploy-username <login> --xl-deploy-password <password> -f xebialabs.yaml
````

