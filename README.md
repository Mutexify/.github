# Mutexify

## Description

Proof of concept application to provide a reliable locking mechanism for resources across the web that acts as such a distributed mutex. 

The main building block of the functionality is the lock slot along with its state, which represents any type of resource and has only one source of truth. The user sends a request to the system to access a resource, then the system processes the request and returns the result, giving or denying access to the resource to the user. Slot access requests are sent as messages through a queue and are processed synchronously by a single function, ensuring consistency.

## Example of use

Two programmers want to use a shared sandbox environment and not interfere with each other.

![](https://github.com/Mutexify/.github/blob/main/profile/demo.gif)

## Tech stack

System is designed for Azure cloud. It consists of frontend and backend of application, lambda function for synchronously processing locks, message queues (service bus) for communication between modules and non-relational database for persisting locks. Logs and monitoring is managed through Application Insights. Additionaly, external service can be attached through web hook (event grid) for notifications about lock changes.

Code for modules is written in TypeScript, authorization is done with Google OAuth.

## Repositories

### Frontface

Web app providing functionality to register new lock slot and manage existing locks. Frontface also manages authorization and authentication.

### Frontface-client

UI for Frontface app.

### Lockkeeper

Lambda function for processing of lock requests. There is only one instance of this service, and it synchronously processes messages from queue, guaranteeing consistency.

## Component diagram


![Exported-Diagram (3)](https://github.com/Mutexify/.github/assets/57150712/a0aec7bb-5f88-4db2-8683-6c4578dfa747)


Diagram is also available on https://azurediagrams.com/KLINkWle.
