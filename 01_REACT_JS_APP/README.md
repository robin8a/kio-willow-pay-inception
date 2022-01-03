
# References
- [Amplify Getting Started](https://docs.amplify.aws/start)
- [Policy AWS Simulator](https://policysim.aws.amazon.com)
- [Scalar types in AWS AppSync](https://docs.aws.amazon.com/appsync/latest/devguide/scalars.html)
- [GraphQL API Security with AWS AppSync and Amplify](https://aws.amazon.com/blogs/mobile/graphql-security-appsync-amplify/)
- https://tokhun.io/explore/serialized/jVRMXB
- https://docs.ipfs.io/concepts/what-is-ipfs/
- https://www.europapress.es/economia/finanzas-00340/noticia-mito-galeria-arte-nft-hispanohablantes-abre-puertas-20210916183841.html
- https://js.ipfs.io/

# Starting React App

```sh
# https://github.com/robin8a/kio-arsser-nft-inception.git

source ~/.bash_profile
npx create-react-app kio-arsser-nft-rjs-app
```

# Design

- [Paper Kit React is a freeby Bootstrap 4, React and Reactstrap UI Kit.](https://demos.creative-tim.com/paper-kit-react/#/documentation/introduction?ref=pkr-github-readme)


1. [Download](https://www.creative-tim.com/product/now-ui-kit-pro-react) the template 
2. Unzip
3. Copy dependencies from template package.json to kio-jup-places-reserve-rjs-app/package.json (Also contains react-player)
```json
{
  "name": "kio-sl-video-history-board-rjs-app",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.11.4",
    "@testing-library/react": "^11.1.0",
    "@testing-library/user-event": "^12.1.10",
    "react": "^17.0.2",
    "react-dom": "^17.0.2",
    "react-scripts": "4.0.3",
    "web-vitals": "^1.0.1",
    "@aws-amplify/ui-react": "^1.2.8",
    "@material-ui/core": "^4.12.3",
    "@material-ui/icons": "^4.11.2",
    "aws-amplify": "^4.2.2",
    "aws-amplify-react": "^5.0.8",
    "bootstrap": "^5.0.2",
    "i": "^0.3.6",
    "moment": "2.29.1",
    "node-sass": "^6.0.1",
    "nouislider": "15.1.0",
    "npm": "^7.20.5",
    "react-bootstrap": "^2.0.0-beta.4",
    "react-bootstrap-switch": "15.5.3",
    "react-player": "^2.6.1",
    "react-router": "5.2.0",
    "react-router-dom": "5.2.0",
    "react-select": "^4.3.1",
    "reactstrap": "8.9.0",
    "styled-components": "^5.3.0"
  }
```
4. Install template dependencies
```sh
npm install
npm audit fix
```
5. Copy jsconfig.json from template to project root 
6. Copy folders (assets, components, views) to src/
7. Add "imports " index.js

```js
import React from 'react';
import ReactDOM from 'react-dom';
// styles
import 'bootstrap/dist/css/bootstrap.min.css';
import "assets/css/paper-kit.css";
import "assets/demo/demo.css";

import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';


ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();


```
8. Conf app.js like this:

```js
import React, { Component } from 'react'
// import { Container } from 'react-bootstrap'
// Components
// import Home from './components/Home'
// import Header from './components/Header/Header'
import Footer from './components/Footers/DemoFooter'

// pages
import Index from "views/Index.js";
import NucleoIcons from "views/NucleoIcons.js";
import LandingPage from "views/examples/LandingPage.js";
import ProfilePage from "views/examples/ProfilePage.js";
import RegisterPage from "views/examples/RegisterPage.js";

// Routing
import { BrowserRouter as Router, Switch, Route, Redirect } from 'react-router-dom'

class App extends Component{
  
  constructor() {
    super();
    this.state = {
      x: 0,
      y: 0,
      epochTime: 0
    }
  }

  
  render() {
    
    return (   
      <Router>

          <Switch>
            <Route path="/index" render={(props) => <Index {...props} />} />
            <Route
              path="/nucleo-icons"
              render={(props) => <NucleoIcons {...props} />}
            />
            <Route
              path="/landing-page"
              render={(props) => <LandingPage {...props} />}
            />
            <Route
              path="/profile-page"
              render={(props) => <ProfilePage {...props} />}
            />
            <Route
              path="/register-page"
              render={(props) => <RegisterPage {...props} />}
            />
            <Redirect to="/landing-page" />
          </Switch>


        <Footer/>
      </Router>
    )
  }
}

export default App
```


# Dependencies
```sh
npm i aws-amplify @aws-amplify/ui-react \
npm i aws-amplify-react \
npm install react-bootstrap@next bootstrap@5.1.0 \
npm i react-select \
npm install @material-ui/core \
npm install @material-ui/icons \
npm install react-router-dom \
npm install react-player
```

# Amplify

## configure

- Just when is a new aws account
```sh
amplify configure
```


## init

```sh
amplify init
# Note: It is recommended to run this command from the root of your app directory
# ? Enter a name for the project kiowillowpayrjsapp
# ? Enter a name for the environment kwipayenv
# ? Choose your default editor: Visual Studio Code
# ? Choose the type of app that you're building javascript
# Please tell us about your project
# ? What javascript framework are you using react
# ? Source Directory Path:  src
# ? Distribution Directory Path: build
# ? Build Command:  npm run-script build
# ? Start Command: npm run-script start
# Using default provider  awscloudformation

# For more information on AWS Profiles, see:
# https://docs.aws.amazon.com/cli/latest/userguide/cli-multiple-profiles.html

# ? Do you want to use an AWS profile? Yes
# ? Please choose the profile you want to use kio-willow-pay
# Adding backend environment kwipayenv to AWS Amplify Console app: d2p7cnbefaaed7
# ⠴ Initializing project in the cloud...

# CREATE_IN_PROGRESS UnauthRole                                  AWS::IAM::Role             Wed Nov 03 2021 10:34:54 GMT-0500 (Colombia Standard Time)               
# CREATE_IN_PROGRESS AuthRole                                    AWS::IAM::Role             Wed Nov 03 2021 10:34:54 GMT-0500 (Colombia Standard Time)               
# CREATE_IN_PROGRESS DeploymentBucket                            AWS::S3::Bucket            Wed Nov 03 2021 10:34:54 GMT-0500 (Colombia Standard Time)               
# CREATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446 AWS::CloudFormation::Stack Wed Nov 03 2021 10:34:49 GMT-0500 (Colombia Standard Time) User Initiated
# ⠴ Initializing project in the cloud...

# CREATE_IN_PROGRESS UnauthRole       AWS::IAM::Role  Wed Nov 03 2021 10:34:55 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS AuthRole         AWS::IAM::Role  Wed Nov 03 2021 10:34:55 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS DeploymentBucket AWS::S3::Bucket Wed Nov 03 2021 10:34:55 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# ⠦ Initializing project in the cloud...

# CREATE_COMPLETE AuthRole   AWS::IAM::Role Wed Nov 03 2021 10:35:10 GMT-0500 (Colombia Standard Time) 
# CREATE_COMPLETE UnauthRole AWS::IAM::Role Wed Nov 03 2021 10:35:10 GMT-0500 (Colombia Standard Time) 
# ⠧ Initializing project in the cloud...

# CREATE_COMPLETE amplify-kiowillowpayrjsapp-kwipayenv-103446 AWS::CloudFormation::Stack Wed Nov 03 2021 10:35:18 GMT-0500 (Colombia Standard Time) 
# CREATE_COMPLETE DeploymentBucket                            AWS::S3::Bucket            Wed Nov 03 2021 10:35:16 GMT-0500 (Colombia Standard Time) 
# ✔ Successfully created initial AWS cloud resources for deployments.
# ✔ Initialized provider successfully.
# Initialized your environment successfully.

# Your project has been successfully initialized and connected to the cloud!

# Some next steps:
# "amplify status" will show you what you've added already and if it's locally configured or deployed
# "amplify add <category>" will allow you to add features like user login or a backend API
# "amplify push" will build all your local backend resources and provision it in the cloud
# “amplify console” to open the Amplify Console and view your project status
# "amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

# Pro tip:
# Try "amplify add api" to create a backend API and then "amplify publish" to deploy everything
```

# Codecommit

- [Create repo](https://docs.aws.amazon.com/cli/latest/reference/codecommit/create-repository.html)
- 
```sh
nano ~/.aws/credentials
export PATH=~/Library/Python/3.8/bin:$PATH
# source ~/.bash_profile
# Test
aws s3 ls --profile kio-willow-pay
export AWS_PROFILE=kio-willow-pay

# aws codecommit create-repository --repository-name MyDemoRepo --repository-description "My demonstration repository" --tags Team=Saanvi
aws codecommit create-repository --repository-name kio-willow-pay-rjs-app --repository-description "Willow Pay Market" --tags Team=kio --region us-east-1 

```

## result
```json
{
    "repositoryMetadata": {
        "accountId": "228655235420",
        "repositoryId": "9e1b0aba-4e77-4e97-834a-41c12de4d08d",
        "repositoryName": "kio-willow-pay-rjs-app",
        "repositoryDescription": "Willow Pay Market",
        "lastModifiedDate": "2021-11-03T10:38:54.228000-05:00",
        "creationDate": "2021-11-03T10:38:54.228000-05:00",
        "cloneUrlHttp": "https://git-codecommit.us-east-1.amazonaws.com/v1/repos/kio-willow-pay-rjs-app",
        "cloneUrlSsh": "ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/kio-willow-pay-rjs-app",
        "Arn": "arn:aws:codecommit:us-east-1:228655235420:kio-willow-pay-rjs-app"
    }
}}
```


# git

```sh
ssh-keygen
/Users/robin8a/.ssh/kio_willow_pay_codecommit_rsa

cat ~/.ssh/kio_willow_pay_codecommit_rsa.pub

```


```sh
cd ~/.ssh
ls
nano config

# Add

# CodeCommit hosts
Host kio_willow_pay_codecommit_rsa
   HostName git-codecommit.us-east-1.amazonaws.com
   User APKATKPHKAFOPODPAEGB
   IdentityFile ~/.ssh/kio_willow_pay_codecommit_rsa

```

<!-- https://xiaolishen.medium.com/use-multiple-ssh-keys-for-different-github-accounts-on-the-same-computer-7d7103ca8693 -->

```sh
# git remote -v
# git remote rm origin
# git init
git remote add origin ssh://kio_willow_pay_codecommit_rsa/v1/repos/kio-willow-pay-rjs-app
git push --set-upstream origin master
git push
```


# Amplify hosting

## Result
```sh
amplify add hosting                  
? Select the plugin module to execute Hosting with Amplify Console (Managed hos
ting with custom domains, Continuous deployment)
? Choose a type Continuous deployment (Git-based deployments)
? Continuous deployment is configured in the Amplify Console. Please hit enter 
once you connect your repository 
Amplify hosting urls: 
┌──────────────┬──────────────────────────────────────────────┐
│ FrontEnd Env │ Domain                                       │
├──────────────┼──────────────────────────────────────────────┤
│ master       │ https://master.d2p7cnbefaaed7.amplifyapp.com │
└──────────────┴──────────────────────────────────────────────┘
```

# Amplify auth

```sh
amplify add auth

# Using service: Cognito, provided by: awscloudformation
 
#  The current configured provider is Amazon Cognito. 
 
#  Do you want to use the default authentication and security configuration? Defa
# ult configuration
#  Warning: you will not be able to edit these selections. 
#  How do you want users to be able to sign in? Username
#  Do you want to configure advanced settings? No, I am done.
# Successfully added resource kiowillowpayrjsapp80d6f39b locally

# Some next steps:
# "amplify push" will build all your local backend resources and provision it in the cloud
# "amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

```

# Amplify push

```sh
amplify push
```

# Amplify api

```sh
amplify add api
? Please select from one of the below mentioned services: GraphQL
? Provide API name: kiowillowpayrjsapp
? Choose the default authorization type for the API Amazon Cognito User Pool
Use a Cognito user pool configured as a part of this project.
? Do you want to configure advanced settings for the GraphQL API No, I am done.


? Do you have an annotated GraphQL schema? No
? Do you want a guided schema creation? Yes
? What best describes your project: Objects with fine-grained access control (e
.g., a project management app with owner-based authorization)
? Do you want to edit the schema now? Yes
Please edit the file in your editor: /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema.graphql
? Press enter to continue 

The following types do not have '@auth' enabled. Consider using @auth with @model
         - User
         - Measure
         - Product
         - Price
Learn more about @auth here: https://aws-amplify.github.io/docs/cli-toolchain/graphql#auth 


GraphQL schema compiled successfully.

Edit your schema at /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema.graphql or place .graphql files in a directory at /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema
Successfully added resource kiowillowpayrjsapp locally

Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud
```


# amplify storage
```sh
amplify add storage
# ? Please select from one of the below mentioned services: Content (Images, audio, video, etc.)
# ? Please provide a friendly name for your resource that will be used to label this category in the project: s32d231932
# ? Please provide bucket name: kioslvideohistoryboa7f757aaf029b451aab9ce97b95c
# ? Who should have access: Auth and guest users
# ? What kind of access do you want for Authenticated users? create/update, read
# ? What kind of access do you want for Guest users? read
# ? Do you want to add a Lambda Trigger for your S3 Bucket? No
# Successfully updated auth resource locally.
# Successfully added resource s32d231932 locally

# Some next steps:
# "amplify push" builds all of your local backend resources and provisions them in the cloud
# "amplify publish" builds all of your local backend and front-end resources (if you added hosting category) and provisions them in the cloud

kioslvideohistoryboard
```


# Amplify API

```sh
amplify add api
# ? Please select from one of the below mentioned services: GraphQL
# ? Provide API name: kiojupplacesreserver
# ? Choose the default authorization type for the API API key
# ? Enter a description for the API key: 
# ? After how many days from now the API key should expire (1-365): 365
# ? Do you want to configure advanced settings for the GraphQL API No, I am done.
# ? Do you have an annotated GraphQL schema? No
# ? Do you want a guided schema creation? Yes
# ? What best describes your project: One-to-many relationship (e.g., “Blogs” with “Posts” and “Comments”)
# ? Do you want to edit the schema now? Yes
# Please edit the file in your editor: /Users/robin8a/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema.graphql
# ? Press enter to continue 

# The following types do not have '@auth' enabled. Consider using @auth with @model
#          - Place
#          - Reserve
# Learn more about @auth here: https://aws-amplify.github.io/docs/cli-toolchain/graphql#auth 


# GraphQL schema compiled successfully.

# Edit your schema at /Users/robin8a/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema.graphql or place .graphql files in a directory at /Users/robin8a/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema
# Successfully added resource kiojupplacesreserver locally

# Some next steps:
# "amplify push" will build all your local backend resources and provision it in the cloud
# "amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

```

## Result

```sh
amplify push   
# ✔ Successfully pulled backend environment kiojuplrev from the cloud.

# Current Environment: kiojuplrev

# | Category | Resource name                | Operation | Provider plugin   |
# | -------- | ---------------------------- | --------- | ----------------- |
# | Api      | kiojupplacesreserver         | Create    | awscloudformation |
# | Hosting  | amplifyhosting               | No Change |                   |
# | Auth     | kiojupplacesreserver83258164 | No Change | awscloudformation |
# ? Are you sure you want to continue? Yes

# The following types do not have '@auth' enabled. Consider using @auth with @model
#          - Place
#          - Reserve
# Learn more about @auth here: https://aws-amplify.github.io/docs/cli-toolchain/graphql#auth 


# GraphQL schema compiled successfully.

# Edit your schema at /Users/robin8a/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema.graphql or place .graphql files in a directory at /Users/robin8a/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema
# ? Do you want to generate code for your newly created GraphQL API Yes
# ? Choose the code generation language target javascript
# ? Enter the file name pattern of graphql queries, mutations and subscriptions src/graphql/**/*.js
# ? Do you want to generate/update all possible GraphQL operations - queries, mutations and subscriptions Yes
# ? Enter maximum statement depth [increase from default if your schema is deeply nested] 2
# ⠙ Updating resources in the cloud. This may take a few minutes...

# UPDATE_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031 AWS::CloudFormation::Stack Fri Aug 06 2021 16:11:45 GMT-0500 (Colombia Standard Time) User Initiated
# ⠇ Updating resources in the cloud. This may take a few minutes...

# UPDATE_IN_PROGRESS authkiojupplacesreserver83258164 AWS::CloudFormation::Stack Fri Aug 06 2021 16:11:51 GMT-0500 (Colombia Standard Time) 
# CREATE_IN_PROGRESS apikiojupplacesreserver          AWS::CloudFormation::Stack Fri Aug 06 2021 16:11:51 GMT-0500 (Colombia Standard Time) 
# ⠴ Updating resources in the cloud. This may take a few minutes...

# UPDATE_COMPLETE    authkiojupplacesreserver83258164 AWS::CloudFormation::Stack Fri Aug 06 2021 16:11:52 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS apikiojupplacesreserver          AWS::CloudFormation::Stack Fri Aug 06 2021 16:11:52 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# ⠋ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-1VMDXWBKYEZ81 AWS::CloudFormation::Stack Fri Aug 06 2021 16:11:52 GMT-0500 (Colombia Standard Time) User Initiated
# ⠋ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS GraphQLAPI AWS::AppSync::GraphQLApi Fri Aug 06 2021 16:11:57 GMT-0500 (Colombia Standard Time) 
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    GraphQLAPI AWS::AppSync::GraphQLApi Fri Aug 06 2021 16:12:00 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS GraphQLAPI AWS::AppSync::GraphQLApi Fri Aug 06 2021 16:12:00 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    GraphQLSchema AWS::AppSync::GraphQLSchema Fri Aug 06 2021 16:12:06 GMT-0500 (Colombia Standard Time)                            
# CREATE_COMPLETE    GraphQLAPIKey AWS::AppSync::ApiKey        Fri Aug 06 2021 16:12:06 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS GraphQLAPIKey AWS::AppSync::ApiKey        Fri Aug 06 2021 16:12:06 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS GraphQLSchema AWS::AppSync::GraphQLSchema Fri Aug 06 2021 16:12:05 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS GraphQLAPIKey AWS::AppSync::ApiKey        Fri Aug 06 2021 16:12:03 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS GraphQLSchema AWS::AppSync::GraphQLSchema Fri Aug 06 2021 16:12:03 GMT-0500 (Colombia Standard Time)                            
# ⠙ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS Place   AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:09 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS Reserve AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:09 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS Place   AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:08 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS Reserve AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:08 GMT-0500 (Colombia Standard Time)                            
# ⠧ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-1VMDXWBKYE-Place-17BAOD8XXTD8Q AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:09 GMT-0500 (Colombia Standard Time) User Initiated
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-1VMDXWBK-Reserve-NK4N0JJCMGNJ AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:09 GMT-0500 (Colombia Standard Time) User Initiated
# ⠼ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS PlaceTable   AWS::DynamoDB::Table Fri Aug 06 2021 16:12:17 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS PlaceIAMRole AWS::IAM::Role       Fri Aug 06 2021 16:12:16 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS PlaceTable   AWS::DynamoDB::Table Fri Aug 06 2021 16:12:16 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS PlaceIAMRole AWS::IAM::Role       Fri Aug 06 2021 16:12:16 GMT-0500 (Colombia Standard Time)                            
# ⠴ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS ReserveIAMRole AWS::IAM::Role       Fri Aug 06 2021 16:12:17 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS ReserveTable   AWS::DynamoDB::Table Fri Aug 06 2021 16:12:16 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS ReserveTable   AWS::DynamoDB::Table Fri Aug 06 2021 16:12:16 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS ReserveIAMRole AWS::IAM::Role       Fri Aug 06 2021 16:12:16 GMT-0500 (Colombia Standard Time)                            
# ⠴ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE PlaceIAMRole AWS::IAM::Role Fri Aug 06 2021 16:12:30 GMT-0500 (Colombia Standard Time) 
# ⠦ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE ReserveIAMRole AWS::IAM::Role Fri Aug 06 2021 16:12:31 GMT-0500 (Colombia Standard Time) 
# ⠴ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    PlaceDataSource AWS::AppSync::DataSource Fri Aug 06 2021 16:12:35 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS PlaceDataSource AWS::AppSync::DataSource Fri Aug 06 2021 16:12:35 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS PlaceDataSource AWS::AppSync::DataSource Fri Aug 06 2021 16:12:33 GMT-0500 (Colombia Standard Time)                            
# ⠦ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    ReserveDataSource AWS::AppSync::DataSource Fri Aug 06 2021 16:12:35 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS ReserveDataSource AWS::AppSync::DataSource Fri Aug 06 2021 16:12:35 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS ReserveDataSource AWS::AppSync::DataSource Fri Aug 06 2021 16:12:33 GMT-0500 (Colombia Standard Time)                            
# ⠼ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS GetPlaceResolver    AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time) 
# CREATE_IN_PROGRESS CreatePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time) 
# CREATE_IN_PROGRESS ListPlaceResolver   AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time) 
# CREATE_IN_PROGRESS UpdatePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time) 
# ⠦ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS ListReserveResolver   AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time) 
# CREATE_IN_PROGRESS DeleteReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time) 
# ⠴ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    DeletePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:41 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS DeletePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    GetPlaceResolver    AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_COMPLETE    CreatePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS GetPlaceResolver    AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    UpdatePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS CreatePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS UpdatePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    ListPlaceResolver   AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS ListPlaceResolver   AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS DeletePlaceResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time)                            
# ⠦ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    CreateReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:41 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS CreateReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:41 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    UpdateReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:41 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS UpdateReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:41 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    DeleteReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS DeleteReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    GetReserveResolver    AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_COMPLETE    ListReserveResolver   AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS GetReserveResolver    AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS ListReserveResolver   AWS::AppSync::Resolver Fri Aug 06 2021 16:12:40 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS CreateReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:39 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS GetReserveResolver    AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS UpdateReserveResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:12:38 GMT-0500 (Colombia Standard Time)                            
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE PlaceTable AWS::DynamoDB::Table Fri Aug 06 2021 16:12:48 GMT-0500 (Colombia Standard Time) 
# ⠏ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE ReserveTable AWS::DynamoDB::Table Fri Aug 06 2021 16:12:48 GMT-0500 (Colombia Standard Time) 
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-1VMDXWBKYE-Place-17BAOD8XXTD8Q AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:50 GMT-0500 (Colombia Standard Time) 
# ⠋ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-1VMDXWBK-Reserve-NK4N0JJCMGNJ AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:50 GMT-0500 (Colombia Standard Time) 
# ⠋ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE Reserve AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:57 GMT-0500 (Colombia Standard Time) 
# ⠋ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE Place AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:57 GMT-0500 (Colombia Standard Time) 
# ⠋ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS ConnectionStack AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:00 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS ConnectionStack AWS::CloudFormation::Stack Fri Aug 06 2021 16:12:59 GMT-0500 (Colombia Standard Time)                            
# ⠦ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-ConnectionStack-TIRY9TBK0P36 AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:00 GMT-0500 (Colombia Standard Time) User Initiated
# ⠧ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS ReserveplaceResolver  AWS::AppSync::Resolver Fri Aug 06 2021 16:13:06 GMT-0500 (Colombia Standard Time) 
# CREATE_IN_PROGRESS PlacereservesResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:13:05 GMT-0500 (Colombia Standard Time) 
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE    ReserveplaceResolver  AWS::AppSync::Resolver Fri Aug 06 2021 16:13:08 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS ReserveplaceResolver  AWS::AppSync::Resolver Fri Aug 06 2021 16:13:08 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_COMPLETE    PlacereservesResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:13:08 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS PlacereservesResolver AWS::AppSync::Resolver Fri Aug 06 2021 16:13:07 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# ⠼ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE ConnectionStack AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:11 GMT-0500 (Colombia Standard Time) 
# ⠹ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS CustomResourcesjson AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:14 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS CustomResourcesjson AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:13 GMT-0500 (Colombia Standard Time)                            
# ⠧ Updating resources in the cloud. This may take a few minutes...

# CREATE_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreser-CustomResourcesjson-5C95OXAUGBTW AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:14 GMT-0500 (Colombia Standard Time) User Initiated
# ⠇ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreser-CustomResourcesjson-5C95OXAUGBTW AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:18 GMT-0500 (Colombia Standard Time) 
# ⠼ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE CustomResourcesjson AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:25 GMT-0500 (Colombia Standard Time) 
# ⠸ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE amplify-kiojupplacesreserver-kiojuplrev-94031-apikiojupplacesreserver-1VMDXWBKYEZ81 AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:27 GMT-0500 (Colombia Standard Time) 
# ⠏ Updating resources in the cloud. This may take a few minutes...

# CREATE_COMPLETE apikiojupplacesreserver AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:46 GMT-0500 (Colombia Standard Time) 
# ⠇ Updating resources in the cloud. This may take a few minutes...

# UPDATE_COMPLETE                     amplify-kiojupplacesreserver-kiojuplrev-94031 AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:51 GMT-0500 (Colombia Standard Time) 
# UPDATE_COMPLETE                     authkiojupplacesreserver83258164              AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:50 GMT-0500 (Colombia Standard Time) 
# UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiojupplacesreserver-kiojuplrev-94031 AWS::CloudFormation::Stack Fri Aug 06 2021 16:13:49 GMT-0500 (Colombia Standard Time) 
# ✔ Generated GraphQL operations successfully and saved at src/graphql
# ✔ All resources are updated in the cloud

GraphQL endpoint: https://oq2wwe5hgjegzltql7ol77uzxq.appsync-api.us-east-1.amazonaws.com/graphql
GraphQL API KEY: da2-5golr3ets5cglf4qk6x5m6uini

```


QmVnv4YKRU9qtGPMWDVeDXd7VEbGwsBHZnDuqFXUxCKDcS

https://ipfs.io/ipfs/QmVnv4YKRU9qtGPMWDVeDXd7VEbGwsBHZnDuqFXUxCKDcS


# Setting Up authorization

https://docs.amplify.aws/cli-legacy/graphql-transformer/auth/#combining-multiple-authorization-types

```json
type Post @model
  @auth (
    rules: [
      # allow all authenticated users ability to create posts
      # allow owners ability to update and delete their posts
      { allow: owner },

      # allow all authenticated users to read posts
      { allow: private, operations: [read] },

      # allow all guest users (not authenticated) to read posts
      { allow: public, operations: [read] }
    ]
  ) {
  id: ID!
  title: String
  owner: String
}
```
## 
- [Using multiple authorization types with AWS AppSync GraphQL APIs](https://aws.amazon.com/blogs/mobile/using-multiple-authorization-types-with-aws-appsync-graphql-apis/)


## Updating Auth

```sh
amplify update auth
Please note that certain attributes may not be overwritten if you choose to use defaults settings.

You have configured resources that might depend on this Cognito resource.  Updating this Cognito resource could have unintended side effects.

Using service: Cognito, provided by: awscloudformation
 What do you want to do? Create or update Cognito user pool groups
? Provide a name for your user pool group: Administrators
? Do you want to add another User Pool Group Yes
? Provide a name for your user pool group: RestaurantManagers
? Do you want to add another User Pool Group Yes
? Provide a name for your user pool group: Willers
? Do you want to add another User Pool Group No
✔ Sort the user pool groups in order of preference · Administrators, RestaurantManagers, Willers
Successfully updated auth resource kiowillowpayrjsapp80d6f39b locally

Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

Successfully updated resource kiowillowpayrjsapp80d6f39b locally

Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud
```



# Changin Auth Default

```sh
amplify update api
? Please select from one of the below mentioned services: GraphQL
? Select from the options below Walkthrough all configurations
? Choose the default authorization type for the API API key
? Enter a description for the API key: allguestusers
? After how many days from now the API key should expire (1-365): 365
? Do you want to configure advanced settings for the GraphQL API No, I am done.

The following types do not have '@auth' enabled. Consider using @auth with @model
         - User
         - Measure
         - Category
         - Product
         - Price
         - Discount
         - Order
         - Feature
         - Purchase
Learn more about @auth here: https://docs.amplify.aws/cli/graphql-transformer/auth


GraphQL schema compiled successfully.

Edit your schema at /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema.graphql or place .graphql files in a directory at /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema
The API_KEY auth type has been added to the API.
⚠️  If other resources depend on this API and need access to the API key, run "amplify update <category>" and reselect this API as a dependency to add the API key dependency.
Successfully updated resource
➜  kio-willow-pay-rjs-app git:(development) ✗ amplify status

    Current Environment: kwipayenv
    
┌──────────┬────────────────────────────┬───────────┬───────────────────┐
│ Category │ Resource name              │ Operation │ Provider plugin   │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Api      │ kiowillowpayrjsapp         │ Update    │ awscloudformation │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Hosting  │ amplifyhosting             │ No Change │                   │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Auth     │ kiowillowpayrjsapp80d6f39b │ No Change │ awscloudformation │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Auth     │ userPoolGroups             │ No Change │ awscloudformation │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Storage  │ s363b65c88                 │ No Change │ awscloudformation │
└──────────┴────────────────────────────┴───────────┴───────────────────┘

GraphQL endpoint: https://btodi5nln5gt5bikhcozbzf26q.appsync-api.us-east-1.amazonaws.com/graphql
GraphQL API is configured to use API_KEY authentication, but API Key deployment is disabled, don't forget to create one.


Amplify hosting urls: 
┌──────────────┬──────────────────────────────────────────────┐
│ FrontEnd Env │ Domain                                       │
├──────────────┼──────────────────────────────────────────────┤
│ master       │ https://master.d2p7cnbefaaed7.amplifyapp.com │
│              ├──────────────────────────────────────────────┤
│              │ https://willowpay.co                         │
│              ├──────────────────────────────────────────────┤
│              │ https://www.willowpay.co                     │
└──────────────┴──────────────────────────────────────────────┘
➜  kio-willow-pay-rjs-app git:(development) ✗ amplify push
✔ Successfully pulled backend environment kwipayenv from the cloud.

    Current Environment: kwipayenv
    
┌──────────┬────────────────────────────┬───────────┬───────────────────┐
│ Category │ Resource name              │ Operation │ Provider plugin   │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Api      │ kiowillowpayrjsapp         │ Update    │ awscloudformation │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Hosting  │ amplifyhosting             │ No Change │                   │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Auth     │ kiowillowpayrjsapp80d6f39b │ No Change │ awscloudformation │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Auth     │ userPoolGroups             │ No Change │ awscloudformation │
├──────────┼────────────────────────────┼───────────┼───────────────────┤
│ Storage  │ s363b65c88                 │ No Change │ awscloudformation │
└──────────┴────────────────────────────┴───────────┴───────────────────┘
? Are you sure you want to continue? Yes

The following types do not have '@auth' enabled. Consider using @auth with @model
         - User
         - Measure
         - Category
         - Product
         - Price
         - Discount
         - Order
         - Feature
         - Purchase
Learn more about @auth here: https://docs.amplify.aws/cli/graphql-transformer/auth


GraphQL schema compiled successfully.

Edit your schema at /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema.graphql or place .graphql files in a directory at /Users/robin8a/Documents/react_ws/kio-willow-pay-rjs-app/amplify/backend/api/kiowillowpayrjsapp/schema
? Do you want to update code for your updated GraphQL API No
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446 AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:11 GMT-0500 (Eastern Standard Time) User Initiated
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS authkiowillowpayrjsapp80d6f39b AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:17 GMT-0500 (Eastern Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS apikiowillowpayrjsapp          AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS storages363b65c88              AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:17 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    authkiowillowpayrjsapp80d6f39b AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:18 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    storages363b65c88              AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:18 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS authuserPoolGroups             AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:21 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:18 GMT-0500 (Eastern Standard Time) User Initiated
⠙ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE authuserPoolGroups AWS::CloudFormation::Stack Wed Dec 01 2021 14:11:22 GMT-0500 (Eastern Standard Time) 
⠧ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS GraphQLAPI AWS::AppSync::GraphQLApi Wed Dec 01 2021 14:11:26 GMT-0500 (Eastern Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE    GraphQLAPI    AWS::AppSync::GraphQLApi Wed Dec 01 2021 14:11:28 GMT-0500 (Eastern Standard Time) 
CREATE_IN_PROGRESS GraphQLAPIKey AWS::AppSync::ApiKey     Wed Dec 01 2021 14:11:31 GMT-0500 (Eastern Standard Time) 
⠹ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS GraphQLSchema AWS::AppSync::GraphQLSchema Wed Dec 01 2021 14:11:32 GMT-0500 (Eastern Standard Time) 
⠼ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS GraphQLAPIKey AWS::AppSync::ApiKey Wed Dec 01 2021 14:11:34 GMT-0500 (Eastern Standard Time) Resource creation Initiated
CREATE_COMPLETE    GraphQLAPIKey AWS::AppSync::ApiKey Wed Dec 01 2021 14:11:34 GMT-0500 (Eastern Standard Time)                            
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE    GraphQLSchema AWS::AppSync::GraphQLSchema Wed Dec 01 2021 14:12:35 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Category      AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:38 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS User          AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:38 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Product       AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Feature       AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Price         AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Purchase      AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Discount      AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Order         AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS Measure       AWS::CloudFormation::Stack  Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WR-Measure-M8MFO691LVO5 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated
⠧ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC-Order-1AE5CFQGDQQPJ AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC-Price-1B37QHXWW5V1O AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated


UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02W-Discount-1PYRX6HKJW115 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02W-Purchase-WPLXVYECD0ES AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated
⠋ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WR-Feature-1KBCD6GWB4UNL AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WR-Product-OVYS9XFGEJT7 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC-User-1HVIUX5UQFN83 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:40 GMT-0500 (Eastern Standard Time) User Initiated


UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02W-Category-1A1ZDD6L3SNY4 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:39 GMT-0500 (Eastern Standard Time) User Initiated
⠼ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS UpdateDiscountResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS ListPriceResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdatePriceResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetPriceResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeletePriceResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS UpdateProductResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetProductResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListProductResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS CreateProductResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeleteProductResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
⠼ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS CreateCategoryResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdateCategoryResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListCategoryResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetCategoryResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeleteCategoryResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS CreateUserResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdateUserResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListUserResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeleteUserResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetUserResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS GetOrderResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListOrderResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeleteOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS CreateOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdateOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CreateOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:53 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    ListOrderResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:53 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    DeleteOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:53 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    UpdateOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:53 GMT-0500 (Eastern Standard Time) 
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS CreatePurchaseResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeletePurchaseResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetPurchaseResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListPurchaseResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdatePurchaseResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CreatePurchaseResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    DeletePurchaseResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    UpdatePurchaseResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    ListPurchaseResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:53 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    GetPurchaseResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:53 GMT-0500 (Eastern Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS ListMeasureResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdateMeasureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeleteMeasureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetMeasureResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS CreateMeasureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    DeleteMeasureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    GetMeasureResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    ListMeasureResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    UpdateMeasureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CreateMeasureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 


UPDATE_IN_PROGRESS CreateDiscountResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListDiscountResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DeleteDiscountResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetDiscountResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CreateDiscountResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    DeleteDiscountResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    UpdateDiscountResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    ListDiscountResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    GetDiscountResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS CreatePriceResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    ListPriceResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    GetPriceResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    UpdatePriceResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    DeletePriceResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CreatePriceResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
⠧ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS DeleteFeatureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:48 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS CreateFeatureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ListFeatureResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS GetFeatureResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS UpdateFeatureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:49 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    DeleteFeatureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    GetFeatureResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CreateFeatureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    ListFeatureResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    UpdateFeatureResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE ListUserResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:50 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE CreateUserResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE UpdateUserResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE DeleteUserResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE GetUserResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
⠹ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE UpdateProductResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE ListProductResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE GetProductResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE CreateProductResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE DeleteProductResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE CreateCategoryResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE UpdateCategoryResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:51 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE GetCategoryResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE DeleteCategoryResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE ListCategoryResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:12:52 GMT-0500 (Eastern Standard Time) 
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE GetOrderResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:12:54 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WR-Feature-1KBCD6GWB4UNL AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:55 GMT-0500 (Eastern Standard Time) 
⠋ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC-User-1HVIUX5UQFN83 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:55 GMT-0500 (Eastern Standard Time) 
⠋ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02W-Category-1A1ZDD6L3SNY4 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:57 GMT-0500 (Eastern Standard Time) 
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02W-Discount-1PYRX6HKJW115 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:56 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC-Order-1AE5CFQGDQQPJ AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:57 GMT-0500 (Eastern Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WR-Product-OVYS9XFGEJT7 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:55 GMT-0500 (Eastern Standard Time) 
⠧ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC-Price-1B37QHXWW5V1O AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:56 GMT-0500 (Eastern Standard Time) 
⠹ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02W-Purchase-WPLXVYECD0ES AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:58 GMT-0500 (Eastern Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE Product  AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE Feature  AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE Category AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE Order    AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE User     AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE Price    AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE Discount AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
⠋ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE Purchase AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:02 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE Measure  AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:03 GMT-0500 (Eastern Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WR-Measure-M8MFO691LVO5 AWS::CloudFormation::Stack Wed Dec 01 2021 14:12:56 GMT-0500 (Eastern Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS ConnectionStack AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:06 GMT-0500 (Eastern Standard Time) 
⠙ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I-ConnectionStack-163F1HEF9JYCX AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:07 GMT-0500 (Eastern Standard Time) User Initiated
⠙ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS PurchaseorderResolver     AWS::AppSync::Resolver Wed Dec 01 2021 14:13:16 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS PricepurchasesResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:13:16 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS OrderuserClientResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:13:16 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS DiscountpurchasesResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:13:16 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ProductpricesResolver     AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS CategoryproductsResolver  AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS PurchaseproductResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS OrderpurchasesResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS PurchasediscountResolver  AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ProductpurchasesResolver  AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS MeasureproductsResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS PriceproductResolver      AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS OrderuserWillerResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS FeaturepurchasesResolver  AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS PurchasefeatureResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS PurchasepriceResolver     AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ProductmeasureResolver    AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
UPDATE_IN_PROGRESS ProductcategoryResolver   AWS::AppSync::Resolver Wed Dec 01 2021 14:13:17 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE PricepurchasesResolver AWS::AppSync::Resolver Wed Dec 01 2021 14:13:18 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE PurchaseorderResolver  AWS::AppSync::Resolver Wed Dec 01 2021 14:13:18 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE ProductpricesResolver  AWS::AppSync::Resolver Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE                     OrderuserClientResolver                                                                              AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     DiscountpurchasesResolver                                                                            AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     MeasureproductsResolver                                                                              AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     FeaturepurchasesResolver                                                                             AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     OrderpurchasesResolver                                                                               AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     PriceproductResolver                                                                                 AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     PurchasefeatureResolver                                                                              AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     OrderuserWillerResolver                                                                              AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     ProductcategoryResolver                                                                              AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     PurchasediscountResolver                                                                             AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     PurchasepriceResolver                                                                                AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     PurchaseproductResolver                                                                              AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:19 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     ProductmeasureResolver                                                                               AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:20 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     ProductpurchasesResolver                                                                             AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:20 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE                     CategoryproductsResolver                                                                             AWS::AppSync::Resolver     Wed Dec 01 2021 14:13:20 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I-ConnectionStack-163F1HEF9JYCX AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:23 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE ConnectionStack AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:29 GMT-0500 (Eastern Standard Time) 
⠹ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS CustomResourcesjson AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:33 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE    CustomResourcesjson AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:33 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446-apikiowillowpayrjsapp-1M1I18CQ02WRC AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:37 GMT-0500 (Eastern Standard Time) 
⠹ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE                     apikiowillowpayrjsapp                       AWS::CloudFormation::Stack Wed Dec 01 2021 14:13:57 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-kiowillowpayrjsapp-kwipayenv-103446 AWS::CloudFormation::Stack Wed Dec 01 2021 14:14:00 GMT-0500 (Eastern Standard Time) 
⠇ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE authuserPoolGroups AWS::CloudFormation::Stack Wed Dec 01 2021 14:14:01 GMT-0500 (Eastern Standard Time) 
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE storages363b65c88 AWS::CloudFormation::Stack Wed Dec 01 2021 14:14:02 GMT-0500 (Eastern Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE apikiowillowpayrjsapp AWS::CloudFormation::Stack Wed Dec 01 2021 14:14:35 GMT-0500 (Eastern Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE authkiowillowpayrjsapp80d6f39b              AWS::CloudFormation::Stack Wed Dec 01 2021 14:14:36 GMT-0500 (Eastern Standard Time) 
UPDATE_COMPLETE amplify-kiowillowpayrjsapp-kwipayenv-103446 AWS::CloudFormation::Stack Wed Dec 01 2021 14:14:37 GMT-0500 (Eastern Standard Time) 
✔ All resources are updated in the cloud

GraphQL endpoint: https://btodi5nln5gt5bikhcozbzf26q.appsync-api.us-east-1.amazonaws.com/graphql
GraphQL API KEY: 
```