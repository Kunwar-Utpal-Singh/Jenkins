Jenkins is the open source automation server used mainly for the contineouse intigration (CI) and contineous delivery/deployment (CD) in software development.
It helps developers automatically Build, test ,deploy application whenever code changes or made.

# Why developers need Jenkins?
before the jenkins developers need to do the these task automatically:
1- Build Application 
2- Run test
3- Deploy the server
These process was slow and sometimes developers face error

But Jenkins made these task automated and easy. so every time task pushed to the repository Jenkings detect and can automatically:
1- Pull the latest code
2- Buid the application
3- Run test
4- Deploy the application.
This process is the part of CI/CD part.

## What is the continuouse integration?
CI is the practice of integration  source code change frequently and integrated codebase in workable state.
Developers frequently merges there code in shared repository(Github)
```hcl
Every time developer pushed the code to the repository:
The system automatically builds the project
Runs tests
Checks if the code works correctly

Example CI tools:
Jenkins
GitHub Actions
GitLab CI/CD
```

```hcl
CI Flow
Developer writes code
Pushes code to GitHub
CI tool automatically:
          Builds the application
          Runs tests
          Detects errors early
```          

# What is the continuous deployment?
When application automatically deploys the code into the server after run test is called Deployment but befor the deployment when there is any intervention manually is call Delivery.

### Continuous Delivery:
```hcl
Code is automatically:
Built
Tested
Prepared for production
```

### simple CI/CD pipeline:
```hcl
Developer
    ↓
GitHub Repository
    ↓
CI Tool (Jenkins)
    ↓
Build Application
    ↓
Run Tests
    ↓
Create Package
    ↓
Deploy to Server / Cloud
```


