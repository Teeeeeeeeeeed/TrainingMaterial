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
- Your User has access to Copilot Studio
- Your DLPs have all the Power Platform, F&O, and Copilot connectors enabled for both the F&O and Dataverse environments.

<br><br>


## Chapter 1 - Copilot studio
For the first exerciser, we need to enable the VT entities:
- "SalesOrderLineV2Entity" and
- "SALESORDERHEADERV4ENTITY"

<br>

### Enable Virtual Entities

Go to make.powerapps.com

Select the right environment! (It's not the one that says "(default)" in the end)

Go to Tables and search for Available Finance and Operations Entity

And click on the Name


<img width="1907" height="840" alt="image" src="https://github.com/user-attachments/assets/4c1a9867-f8be-4ab6-be80-e31ebbff8d90" />
<br><br>
Press Edit:
<img width="1907" height="744" alt="image" src="https://github.com/user-attachments/assets/67074b41-3fdf-4b88-b004-0cc3968bab2c" />
<br><br>

Now filter on the Entity that you want to enable:
<img width="1624" height="590" alt="image" src="https://github.com/user-attachments/assets/bb616ad7-2d14-44ae-b6da-16582c53444f" />

<img width="1175" height="440" alt="image" src="https://github.com/user-attachments/assets/3e8aaf88-b0da-4430-984a-8c2ab4502f5f" />
<br><br>
Select the row and press "Edit row using form"
<img width="1403" height="398" alt="image" src="https://github.com/user-attachments/assets/f76d30d3-aaa3-4a66-a8ee-d5adb3408113" />
<br><br>

Access the record - > Select the Visible check box and Press Save

<img width="996" height="593" alt="image" src="https://github.com/user-attachments/assets/649e33f6-2616-4eb7-804c-771603797f3e" />

<br><br>

Once both virtual entities are enabled, you are good to go!

<br><br>

### Exercise 1 - Working In Copilot Studio

Now go to: <br>
https://copilotstudio.microsoft.com/ <br>
If needed, press enable free trial
Press the Environment top right corner and select the environment that's connected to your F&O environment 
Press "Agents" -> Press the "Copilot for finance and operations apps"

<img width="1910" height="790" alt="image" src="https://github.com/user-attachments/assets/cc9c1433-c6a0-4b59-838d-b5922c4d7551" />

<br><br>


Press Knowledge -> Dataverse 
Search for the tables/entities, select it and press add!
Do the same for the other tables/entities

Go to Topics -> Add a Topic -Select from blank

<img width="1420" height="448" alt="image" src="https://github.com/user-attachments/assets/3308d22e-099a-41e5-b767-8909cd1a35a0" />
<br><br>

In the trigger section, press edit on User says a phrase
Add the following 4 trigger phrases

- How many open orders do we have?
- How many open orders do we have
- Open orders?
-  Open orders


<img width="833" height="676" alt="image" src="https://github.com/user-attachments/assets/7c13e908-314a-486c-8953-5f614aee3bda" />

<br><br>

Click the plus under the Trigger -> Advanced -> Generative Answer

<img width="621" height="659" alt="image" src="https://github.com/user-attachments/assets/c9501180-a15a-485d-aa40-47f611ebbe44" />

<br><br>

Set Search only selected sources <br>
Set 'Sales order headers V4' as Knowledge Source <br>
Set Web search to false <br>
Set the input to : 2How many 'Sales order header V4' records are there where 'Status' equals 'Open order'" <br>
And press save

<img width="822" height="766" alt="image" src="https://github.com/user-attachments/assets/efd6e54a-863e-4405-a086-d88a68b3cbc0" />


<br><br>
Now try it out by adding one of your trigger phrases into the dialogue box down in the bottom right corner <br> <br>
<img width="1425" height="775" alt="image" src="https://github.com/user-attachments/assets/98a908cb-f3f6-4014-a330-b30df5d8eb7b" />

<br><br>

If it all looks good, press Publish in the top right corner

Now try the same in F&O!

<img width="1260" height="750" alt="image" src="https://github.com/user-attachments/assets/e944bdd3-ff4b-4093-aa39-c0ba61c05031" />


<br><br><br>

### Exercise 2.A - Advanced Copilot Studio

Create a new topic!<br>
Let it trigger on phrases like "Open Net Value", "What's the open net value", "Net value"

After the topic, add a question to it <br>
"What legal entity do you want to know the Net Value for?"

Set the Identity to Organisation <br><br>
<img width="434" height="446" alt="image" src="https://github.com/user-attachments/assets/b761b398-86c1-450b-a6a4-3a540c2db410" />


Create the Generative Answer and set the data source to 'Sales Order Lines V2'<br>
Press the 3 dots in the input and formula and past: <br><br>
"Whats the Sum of Net Value for all 'Sales Order Line v2 records where 'Line Status' equals 'Open Order' and  'Company Code' equals " & Topic.Var1
<br><br>

<img width="822" height="632" alt="image" src="https://github.com/user-attachments/assets/e48ad08b-1455-408d-8e28-3b4b5845f3bd" />

<br>

Save and Publish and try!
<br>


### Exercise 2.B - Advanced Copilot Studio

Use your imagination to build a copilot of your choice! <br>
Feel free to add new tables/entities to the knowledge base if you would like!<br>
If you are feeling really wild and crazy, go to Settings and turn on the Respond with dynamic and Deep reasoning! <br><br>

<img width="1015" height="190" alt="image" src="https://github.com/user-attachments/assets/39cde750-5d99-410b-8a05-8703b71d9aad" />

<br><br>

Start by creating a new topic <br>
And allow the copilot to read from a bigger scope of source <br><br>

<img width="760" height="650" alt="image" src="https://github.com/user-attachments/assets/06b3bc5e-7bdf-4279-a2cd-a322751f3560" /> <br><br>

Coolest Copilot with the best use case wins! 

<br><br><br>

## Chapter 2 - Model-driven Apps

### Exercise 3 - Purchase App




















