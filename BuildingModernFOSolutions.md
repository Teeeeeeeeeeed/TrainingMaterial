# Bulding Modern F&O Solutions

## About the workshop
In this workshop, we will take a deep dive into virtual entities and explore the whole new world of possibilities they offer. We will discuss how it has influenced best practices for designing solutions and examine several designs that utilise it.

We will walk you through and do exercises on how you use the virtual entities to build solutions with tools like:
- Copilot Studio
- Power Automate
- Power Apps
<br>

## Pre-requisites

### Attendee Background:
Everybody is welcome to join, the session is designed for individuals coming from the F&O side. You do not need to be a pro in Power Platform, we are here for you.

Developer experience is not required; we will only use drag-and-drop tools.


### Environment

When doing the exercises in this workshop, you need an environment.
You can choose to:

 1. Set up a 30-day trial environment in a  trial tenant or
 2. Bring your own environment.

The safest way to make sure everything is working properly is to set up a trial tenant.

#### Setting up a trial tenant
To use a 30-day trial environment, follow the instructions in this link:

https://medium.com/@ted.ohlsson/setting-up-trial-f-o-environments-on-trial-tenants-1c108da8d59a

Ensure that the environment is set up before the workshop.
There are some steps where you need to wait on background processes, so start setting it up a couple of days before the workshop.
Make sure to install the Virtual entity and Copilot parts as well!

#### Bring your own environment
If you bring your own environment, make sure the following requirements are met:
- The F&O environment is Dataverse-enabled (T2 environment is recommended).
- Working virtual entities enabled in the environment (usually, it works out of the box in all T2 environments)
- Your User has System Administrator security role rights in both F&O and Dataverse
- Your F&O environment has Contoso data or is a fully implemented environment with data.
- Your User has access to Copilot studio
- Your DLPs have all the Power Platform, F&O, and Copilot connectors enabled for both the F&O and Dataverse environments.

<br><br>


## Exercise 1 - Copilot studio
For the first exerciser, we need to enable the VT entities:
- "SalesOrderLineV2Entity" and
- "SALESORDERHEADERV4ENTITY"

<br>
Go to make.powerapps.com

Select the right environment! (it's not the one that says "(default)" in the end)

Go to Tables and search for Available Finance and Operations Entity

And click on the Name


<img width="1907" height="840" alt="image" src="https://github.com/user-attachments/assets/4c1a9867-f8be-4ab6-be80-e31ebbff8d90" />
<br>
Press Edit:
<img width="1907" height="744" alt="image" src="https://github.com/user-attachments/assets/67074b41-3fdf-4b88-b004-0cc3968bab2c" />
<br>

Now filter on the Entity that you want to enable:
<img width="1624" height="590" alt="image" src="https://github.com/user-attachments/assets/bb616ad7-2d14-44ae-b6da-16582c53444f" />

<img width="1175" height="440" alt="image" src="https://github.com/user-attachments/assets/3e8aaf88-b0da-4430-984a-8c2ab4502f5f" />
<br>
Select the row and press "Edit row using form"
<img width="1403" height="398" alt="image" src="https://github.com/user-attachments/assets/f76d30d3-aaa3-4a66-a8ee-d5adb3408113" />







