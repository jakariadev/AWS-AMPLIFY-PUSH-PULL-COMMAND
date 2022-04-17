# STEPS FOR AWS-AMPLIFY-PUSH-PULL-COMMAND
aws amplify push, pull with AWS CLI and some dependency error [pipenv] solve.

## 1. PULL from AWS:
```
amplify pull --appId XXXXXXXXX --envName dev
```

## 2. Give AWS Credentials and Answer the console:
```
 Select the authentication method you want to use: AWS access keys
? accessKeyId:  ********************
? secretAccessKey:  ****************************************
? region:  ***************
Amplify AppID found: xxxxxxxxx. Amplify App name is: Xxxxxxxxxxxxxxx
Backend environment dev found in Amplify Console app: Xxxxxxxxxxxxxxx
? Choose your default editor: **Visual Studio Code**
? Choose the type of app that you're building **javascript**
Please tell us about your project
? What javascript framework are you using **react-native**
? Source Directory Path:  src **[hit space for default]**
? Distribution Directory Path: / **[hit space for default]**
? Build Command:  npm.cmd run-script build **[hit space for default]**
? Start Command: npm.cmd run-script start **[hit space for default]**
? Do you plan on modifying this backend? ** Yes**
```

## 3. To sync future upstream changes.
```
amplify pull
```

## 4. Add Lambda Function from AWS CLI:
```
amplify add function
```
 ### REST OF Function add process:
 ```
  ? Select which capability you want to add: Lambda function (serverless function)
  ? Provide an AWS Lambda function name: **FunctionName**
  ? Choose the runtime that you want to use: **Python**
  Only one template found - using Hello World by default.

  Available advanced settings:
  - Resource access permissions
  - Scheduled recurring invocation
  - Lambda layers configuration
  - Environment variables configuration
  - Secret values configuration

  ? Do you want to configure advanced settings? **No**
  ? Do you want to edit the local lambda function now? **No**
  Successfully added resource FunctionName locally.
  ```
  
## 5. Amplify PUSH
```
amplify push
```

## 6. Error Solve:
  #### Problem 1: [PIPENV]
  #### Solve:
    1. Match the Local Python version with amplify [Python 3.9,3.8 or above version recommanded]
    2. Add **pipenv** to the **environment** variable in **windows**
    3. Uninstall the pipenv with the CMD:  ```pip uninstall pipenv``` or ```pip3 uninstall pipenv```
    4. Install pipenv again ```pip3 install pipenv```

  #### Problem 2: [Python version not matched]
  #### Solve:
    1. Go to **C:\Users\User\Desktop\FolderName\amplify\backend\function\FunctionName**.
    2. Open and Edit **Pipfile**  Replace ```python_version = "3.8"``` [My Amplify Py version] with ```python_version = "3.9"``` [My Local PC Py version].
    3. Save and PUSH again.

## Contact: [email me] 
```jakaria.pust@gmail.com```
