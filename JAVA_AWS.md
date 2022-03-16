
Wiring up an AWS_PROFILE variable for a java project.

Go to "Debug" sidebar -> create launch.json > "Java"

and then add the "env" key

```
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "java",
      "name": "Launch Current File",
      "request": "launch",
      "mainClass": "${file}",
      "env": {
        "AWS_PROFILE": "odos",
      }
    },
    {
      "type": "java",
      "name": "Launch RestApplication",
      "request": "launch",
      "mainClass": "com.metrostar.odos.rest.RestApplication",
      "projectName": "odos-baseline-java-api",
      "env": {
        "AWS_PROFILE": "odos",
      }
    }
  ]
}
```