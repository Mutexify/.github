# Mutexio

## Description

Application provides reliable way to provide locking mechanism across web. Main building block of functionality is lock slot along with its state that has only one source of truth, guaranteeing consistency. 

Link to application: https://gentle-stone-0e40d9a03.4.azurestaticapps.net/

Link to requestbin connected to webhook with locking results: https://public.requestbin.com/r/enjzik7tazoaa/2bHbuhO7QyCvISveouaIZ7WmDsR 

## Repositories

### Frontface

Web app providing functionality to register new lock slot and manage existing locks. Frontface also manages authorization and authentication.

### Frontface-client

Frontend for Frontface.

### Lockkeeper

Lambda function managing lock requests. There is only one instance of this service, and it synchronously processes messages from queue, guaranteeing consistency.

## Component diagram


![Exported-Diagram (3)](https://github.com/Mutexify/.github/assets/57150712/a0aec7bb-5f88-4db2-8683-6c4578dfa747)


Diagram is also available on https://azurediagrams.com/KLINkWle.
