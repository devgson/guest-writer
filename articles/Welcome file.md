# Configuring Auth0 as a Custom Authentication System on Firebase
**TL;DR** In this article,  you will learn how to configure Firebase to use Auth0 as a custom authentication system. To get your feet wet on both technologies and on the integration, you will build a simple real-time chat app that will securely store messages on Firestore (a real-time database provided by Firebase), and that will enable users to authenticate through Auth0.
## Prerequisite 
To be able to follow along with this article, it is required that you have a basic understanding of Node.js and Javascript (ES6 to be precise).

In our application, Node.js will be used as our choice of server side language and NPM as package manager , so you need to have both software installed. You can skip the next section if you have both installed otherwise follow along.
### Installing Node and NPM
Head over to the official [Node.js](https://nodejs.org/) website, on the homepage there should be two big green buttons indicating two versions of Node.js, the first is the LTS (stable) version while the second is the current/cutting edge version. Click on the link of the LTS version and download that. After that, run the downloaded executable file and make sure the installation completes.

NPM comes bundled with Node so that should be installed as well. To ensure that the installation was successful, re-open your terminal and run the following commands `node -v` and then `npm -v`. The first command should indicate the version of Node installed on the system while the latter should indicate the version of NPM installed. 

## What is Firebase
[Firebase](firebase.google.com) is a platform which allows you to quickly develop web and mobile applications. It provides services that can be easily integrated into your project to provide certain functionalities. Some of these services/features provided by Firebase include Cloud Firestore, Firebase Storage, Analytics, etc... In this article, Cloud Firestore will provide the real-time database functionality.

Firestore is a NoSQL database that comes with a plethora of features, most notably the real-time feature, this is made possible through the use of Websockets rather than traditional HTTP. It keeps your data in sync across client apps through realtime listeners and offers offline support so you can build responsive apps that work regardless of Internet connectivity. The Firestore [documentation](https://firebase.google.com/docs/firestore/) explains more of these features in greater depth.

## Why use Firebase and Auth0 together?

##A brief look at how our application will do.
You can integrate an external user system with Firebase. For example, you may already have a pre-existing user database or you may want to integrate with a third-party identity provider that Firebase Authentication doesn’t natively support.

To do this, you can create custom tokens with arbitrary claims identifying the user. These custom tokens can then be used to sign into the Firebase Authentication service on a client application and assume the identity described by the token's claims. This identity will then be used when accessing other Firebase services, such as the Firebase Realtime Database and Cloud Storage.
