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
Everybody is welcome to join, the session is designed for individuals coming from the F&O side. You do not need to be a pro in Power Platform, we are here for you. <br>

Developer experience is not required; we will only use drag-and-drop tools. <br><br>


### Environment

When doing the exercises in this workshop, you need an environment. <br>
You can choose to:<br>
 1. Set up a 30-day trial environment in a  trial tenant or
 2. Bring your own environment.
<br>
The safest way to make sure everything is working properly is to set up a trial tenant.<br><br>

#### Setting up a trial tenant
To use a 30-day trial environment, follow the instructions in this link: <br>

https://medium.com/@ted.ohlsson/setting-up-trial-f-o-environments-on-trial-tenants-1c108da8d59a <br><br>

Ensure that the environment is set up before the workshop.<br>
There are some steps where you need to wait on background processes, so start setting it up a couple of days before the workshop. <br>
Make sure to install the Virtual entity and Copilot parts as well!<br><br>

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

Go to make.powerapps.com <br>
Select the right environment! (It's not the one that says "(default)" in the end) <br>
Go to Tables and search for Available Finance and Operations Entity <br>
And click on the Name <br><br>
<img width="1907" height="840" alt="image" src="https://github.com/user-attachments/assets/4c1a9867-f8be-4ab6-be80-e31ebbff8d90" /> <br><br>

Press Edit:<br><br>
<img width="1907" height="744" alt="image" src="https://github.com/user-attachments/assets/67074b41-3fdf-4b88-b004-0cc3968bab2c" /> <br><br>

Now filter on the Entity that you want to enable:<br><br>
<img width="1624" height="590" alt="image" src="https://github.com/user-attachments/assets/bb616ad7-2d14-44ae-b6da-16582c53444f" /> <br><br>
<img width="1175" height="440" alt="image" src="https://github.com/user-attachments/assets/3e8aaf88-b0da-4430-984a-8c2ab4502f5f" /> <br><br>

Select the row and press "Edit row using form" <br><br>
<img width="1403" height="398" alt="image" src="https://github.com/user-attachments/assets/f76d30d3-aaa3-4a66-a8ee-d5adb3408113" /> <br><br>

Access the record - > Select the Visible check box and Press Save <br><br>
<img width="996" height="593" alt="image" src="https://github.com/user-attachments/assets/649e33f6-2616-4eb7-804c-771603797f3e" /> <br><br>

Once both virtual entities are enabled, you are good to go! <br><br>


### Exercise 1 - Working In Copilot Studio

Now go to: <br>
https://copilotstudio.microsoft.com/ <br>
If needed, press enable free trial <br>
Press the Environment top right corner and select the environment that's connected to your F&O environment <br>
Press "Agents" -> Press the "Copilot for finance and operations apps" <br> <br>
<img width="1910" height="790" alt="image" src="https://github.com/user-attachments/assets/cc9c1433-c6a0-4b59-838d-b5922c4d7551" /> <br><br>


Press Knowledge -> Dataverse <br>
Search for the tables/entities, select it and press add! <br>
Do the same for the other tables/entities <br>
Go to Topics -> Add a Topic -Select from blank <br><br>
<img width="1420" height="448" alt="image" src="https://github.com/user-attachments/assets/3308d22e-099a-41e5-b767-8909cd1a35a0" /> <br><br>

In the trigger section, press edit on User says a phrase <br>
Add the following 4 trigger phrases <br>

- How many open orders do we have?
- How many open orders do we have
- Open orders?
- Open orders


<img width="833" height="676" alt="image" src="https://github.com/user-attachments/assets/7c13e908-314a-486c-8953-5f614aee3bda" /> <br><br>

Click the plus under the Trigger -> Advanced -> Generative Answer <br><br>
<img width="621" height="659" alt="image" src="https://github.com/user-attachments/assets/c9501180-a15a-485d-aa40-47f611ebbe44" /> <br><br>

Set Search only selected sources <br>
Set 'Sales order headers V4' as Knowledge Source <br>
Set Web search to false <br>
Set the input to : 2How many 'Sales order header V4' records are there where 'Status' equals 'Open order'" <br>
And press save <br><br>
<img width="822" height="766" alt="image" src="https://github.com/user-attachments/assets/efd6e54a-863e-4405-a086-d88a68b3cbc0" /> <br><br>

Now try it out by adding one of your trigger phrases into the dialogue box down in the bottom right corner <br> <br><br>
<img width="1425" height="775" alt="image" src="https://github.com/user-attachments/assets/98a908cb-f3f6-4014-a330-b30df5d8eb7b" /> <br><br>

If it all looks good, press Publish in the top right corner <br>
Now try the same in F&O!<br><br>
<img width="1260" height="750" alt="image" src="https://github.com/user-attachments/assets/e944bdd3-ff4b-4093-aa39-c0ba61c05031" /><br><br>
<br>

### Exercise 2.A - Advanced Copilot Studio

Create a new topic!<br>
Let it trigger on phrases like "Open Net Value", "What's the open net value", "Net value" <br>

After the topic, add a question to it <br>
"What legal entity do you want to know the Net Value for?" <br>

Set the Identity to Organisation <br><br>
<img width="434" height="446" alt="image" src="https://github.com/user-attachments/assets/b761b398-86c1-450b-a6a4-3a540c2db410" /> <br><br>


Create the Generative Answer and set the data source to 'Sales Order Lines V2'<br>
Press the 3 dots in the input and formula and past: <br>
"Whats the Sum of Net Value for all 'Sales Order Line v2 records where 'Line Status' equals 'Open Order' and  'Company Code' equals " & Topic.Var1 <br><br>
<img width="822" height="632" alt="image" src="https://github.com/user-attachments/assets/e48ad08b-1455-408d-8e28-3b4b5845f3bd" /> <br><br>

Save and Publish and try! <br>
<br>


### Exercise 2.B - Advanced Copilot Studio

Use your imagination to build a copilot of your choice! <br>
Feel free to add new tables/entities to the knowledge base if you would like!<br>
If you are feeling really wild and crazy, go to Settings and turn on the Respond with dynamic and Deep reasoning! <br><br>
<img width="1015" height="190" alt="image" src="https://github.com/user-attachments/assets/39cde750-5d99-410b-8a05-8703b71d9aad" /> <br><br>

Start by creating a new topic <br>
And allow the copilot to read from a bigger scope of source <br><br>
<img width="760" height="650" alt="image" src="https://github.com/user-attachments/assets/06b3bc5e-7bdf-4279-a2cd-a322751f3560" /> <br><br>

Coolest Copilot with the best use case wins!
<br><br><br>




## Chapter 2 - Model-driven Apps

### Exercise 3 - Purchase App

Let's start this exercise by  going in and making sure the following virtual entities are enabled: 

- VendVendorV2Entity (VendorV2)
- PurchPurchaseOrderHeaderV2Entity ( Purchase order headers V2)
- PurchPurchaseOrderLineCDSEntity (CDS purchase order line entity)
<br>


Do the same steps as we did in [Enable Virtual Entities](https://github.com/Teeeeeeeeeeed/TrainingMaterial/edit/main/BuildingModernFOSolutions.md#enable-virtual-entities)

Let's continue in the Maker portal  (make.powerapps.com)

Make sure you are in the right environment <br><br>


<img width="1376" height="588" alt="image" src="https://github.com/user-attachments/assets/e5f3a273-42db-469e-a3aa-86f5ae24b5c3" /> <br><br>

Then go in and create a new solution <br><br>
<img width="1790" height="645" alt="image" src="https://github.com/user-attachments/assets/c819e81a-fc63-479a-8b7b-5763be204a33" /> <br><br>

Add the 3 tables you just created to that solution by accessing the solution -> Press add existing Tables<br><br>
<img width="1022" height="565" alt="image" src="https://github.com/user-attachments/assets/115afad0-cb8d-483d-9e31-23d0277a3653" /> <br> <br>

Find the 3 tables and run <br><br>
<img width="1367" height="835" alt="image" src="https://github.com/user-attachments/assets/5694c144-4b0f-43ca-9cb6-3607fee8ee9c" /> <br><br>

Select Include All objects for all 3 tables and press Add <br><br>
<img width="1351" height="842" alt="image" src="https://github.com/user-attachments/assets/892fdd0e-76de-4a16-8041-1a859413d078" /> <br><br>

Let's create an App !<br>

In the solution press New -> App -> Modeldriven <br><br>
<img width="1242" height="480" alt="image" src="https://github.com/user-attachments/assets/9bf62108-a760-4aab-8f7d-589e87d3e6fe" /> <br><br>


Name your app "Purchase APP" <br>
Press Create <br>

Start by adding our 3 tables to the app by pressing Data -> Search for the table -> Add to app <br><br>
<img width="679" height="571" alt="image" src="https://github.com/user-attachments/assets/29a47ae8-0a9a-40ec-95ee-cc57dfadd89d" /> <br><br>

First, press Save -> then Press Publish! <br>
Then try the app out by pressing play! <br>
Try it out! <br><br>
<img width="1917" height="800" alt="image" src="https://github.com/user-attachments/assets/8ff461bd-7bee-46b2-b478-9f3aa3853c0f" /> <br><br>

Okay some more work here is obviously needed…… <br>
Let's go back to the app designer <br>
Start with the vendor view by pressing the edit button to the right of it in the navigation <br><br>
<img width="1230" height="716" alt="image" src="https://github.com/user-attachments/assets/dc4e909d-31f4-4499-a832-376b103479a7" /><br><br>

Add the fields you think are appropriate for the list/View <br>
If you want to look at the data to understand what the fields contain, open a new tab and go to tables in the maker portal <br>
Select the table you want to view -> select edit -> Add all columns <br><br>
<img width="1294" height="662" alt="image" src="https://github.com/user-attachments/assets/9906afa3-ca64-407c-a5bc-e014c3eaf821" /> <br><br>
<img width="1870" height="736" alt="image" src="https://github.com/user-attachments/assets/991c7c65-7e51-4891-8d55-843720774861" /> <br><br>

Once you are satisfied, press Save and Publish <br><br>
<img width="1916" height="767" alt="image" src="https://github.com/user-attachments/assets/9b15e152-0e75-480c-a35b-8dabb892bc16" /> <br><br>

Now let's go in and edit the form <br><br>
<img width="1851" height="716" alt="image" src="https://github.com/user-attachments/assets/6593c06b-8e9e-439e-bc28-49ac42cff9fb" /> <br><br>

Add the fields you think are appropriate for the form by double clicking them <br>
Forms usually contain more fields than the views, it’s a drill-down feature. <br><br>
<img width="1542" height="559" alt="image" src="https://github.com/user-attachments/assets/8edd70cf-37a3-4b0e-bca8-978d93fab6f4" /> <br><br>

Make sure to at least have added:<br>
- Name
- City
- Country/Region
- Group
<br>

Also, add a sub grid in the end by pressing <br>
Compoonents -> Subgrid <br>
Select table Purchase Order header V2 <br>
Select Default view All Purchase orders <br>
And press done <br><br>
<img width="1033" height="744" alt="image" src="https://github.com/user-attachments/assets/cdda5356-e84e-4209-850b-b3264058137d" /> <br><br>

Press Save and publish <br>
Play the app again! <br>
Now try creating a new vendor by clicking vendor in your menu -> New <br>
Fill in the needed fields and press Save <br><br>
<img width="1419" height="772" alt="image" src="https://github.com/user-attachments/assets/c9f5bfd8-7702-4d26-a2f4-805afcc8570d" /> <br><br>

Go into F&O, search for vendors in the legal entity that you defined for the vendor. <br>
Can you find it there? <br><br>

Now fix the views and forms for "Purchase order headers V2" and "CDS purchase order line entity" as well.<br>
On the Purchase order headers V2 add a subgrid to CDS purchase order line <br><br>

On the Purchase order headers V2 form, add at least:
- Purchase Order
- Company Code
- Vendor V2
- Vendor Account
<br>

On the CDS purchase order line form add at least add:

- Product Name
- Product Number
- Quantity
- Line number
- Purchase Order Headers V2
- Purchase Order
- Company Code
<br>

Ones you are all done press save and publish <br>
Runn your app agin!<br>
Go to Vendors in the Menu ->, find the vendor you created before and access it <br>
Create a new Purchase Order on it <br><br>
<img width="1854" height="863" alt="image" src="https://github.com/user-attachments/assets/a648646e-24da-42f9-bc3e-73fa0cebaf33" /> <br><br>
<img width="1917" height="817" alt="image" src="https://github.com/user-attachments/assets/c2ae262d-649b-44f9-9e4a-8fa86e8a4ef5" /><br><br>
<img width="1580" height="900" alt="image" src="https://github.com/user-attachments/assets/c177f11e-fc19-42dd-af29-8a0efe8a1242" /><br><br>

Now go into F&O agin, can you find your purchase order and purchase order line? <br><br>

<br><br><br>


## Chapter 3 - Power Automate

### Exercise 4 - Exchange Rate Updater

Let's start this exercise by  going in and making sure the following virtual entities are enabled: 

- ExchangeRateCurrencyPairEntity (Exchange rate currency pair)
- ExchangeRateEntity (Exchange rates)

<br>

Do the same steps as we did in [Enable Virtual Entities](https://github.com/Teeeeeeeeeeed/TrainingMaterial/edit/main/BuildingModernFOSolutions.md#enable-virtual-entities) <br><br>

Let's continue in the Maker portal  (make.powerapps.com) <br><br>

Make sure you are in the right environment <br><br>
<img width="1376" height="588" alt="image" src="https://github.com/user-attachments/assets/e5f3a273-42db-469e-a3aa-86f5ae24b5c3" /> <br><br>

Now open the solution you created before <br><br>
<img width="1372" height="750" alt="image" src="https://github.com/user-attachments/assets/66574190-2e1d-414f-92c7-146b1e4010b3" /> <br><br>

Start by adding the two entities we just enabled to the solution, just as we did in exercise 3.<br><br>

Now let's create a new Power Automate in the solution: <br>
Go: New -> Automation -> Cloud flow - Instant <br><br>

<img width="1604" height="409" alt="image" src="https://github.com/user-attachments/assets/169974a6-ac3e-496f-a8ce-ddfc151f660a" />



Name the Flow "Exchange Rate Updater"<br>
Select" Manually trigger a flow"<br>
Press "Create" <br><br>
<img width="675" height="427" alt="image" src="https://github.com/user-attachments/assets/7f77d80f-5d46-47eb-a6c4-cda94c30716a" /> <br><br>

Press "New Step" <br>
Select the Dataverse "List Rows" Action <br> <br>
<img width="491" height="591" alt="image" src="https://github.com/user-attachments/assets/fbeb3f51-8f45-4c8a-ae53-3dfdec45a6db" /> <br><br>

In the table name select "Exchange rate currency pair (mserp)" <br>
Important! - If you have two ones, select the bottom one. If you have two and select the top one , you will gett an Issue later in the exercise <br>
Press Save <br><br>
<img width="565" height="444" alt="image" src="https://github.com/user-attachments/assets/abc758c7-025a-4ca3-b271-9b72a3df2a8d" /> <br><br>


Change the name of the List rows Action to "Currency Pairs" <br><br>
<img width="730" height="451" alt="image" src="https://github.com/user-attachments/assets/ba451334-5281-4fae-9013-4b78661b20d7" /> <br><br>

Press New step and add a "Apply to each" function <br><br>
<img width="487" height="674" alt="image" src="https://github.com/user-attachments/assets/cd54c904-901b-40c8-b93a-6207d78a153c" /> <br><br>

Select the Currency Pair Value/list of values as output <br>
Select "Add an action"<br><br>
<img width="850" height="643" alt="image" src="https://github.com/user-attachments/assets/063a9a09-5291-40e0-9272-487bd37efc2f" /><br<<br>
<img width="511" height="400" alt="image" src="https://github.com/user-attachments/assets/8d1ab802-e804-4726-b802-e7b011c5eddb" /><br><br>

Select the "Get Exchange Rate Action"<br><br>
<img width="533" height="831" alt="image" src="https://github.com/user-attachments/assets/f1593454-66d5-44f4-a5c4-5b25eddc6530" /> <br><br>
<img width="543" height="680" alt="image" src="https://github.com/user-attachments/assets/af793e58-c0ba-4f77-8a84-d1293e54b6f8" /> <br><br>

Now open a new tab on your browser and go to: https://app.exchangerate-api.com/sign-up <br>
Press Get A Free key and sign up <br>
Once confirmed, your email the API key will then be sent to you via email <br>
Give your connection a name and add the API Key that was sent to you: <br> <br>
<img width="852" height="536" alt="image" src="https://github.com/user-attachments/assets/c8bac7e2-04c1-4e84-9ef5-48c85e8c0f25" /><br><br>
<img width="549" height="618" alt="image" src="https://github.com/user-attachments/assets/e118d2b3-a865-45e3-86e5-2a0ec91ea54b" /><br><br>

Add the From currency (from the Currency Pair) to the Base Currency <br>
Add the To currency (from the Currency Pair) to the Target Currency <br><br>
<img width="837" height="623" alt="image" src="https://github.com/user-attachments/assets/84d154a3-a871-4beb-a3ee-aa4a74586b68" /> <br><br>

Press Add an action <br>
Select the Dataverse "List Rows" Action <br><br>
<img width="650" height="824" alt="image" src="https://github.com/user-attachments/assets/0474aec3-2321-4bfa-a44b-0577e74a0f4e" /> <br><br>

Select Exchange rates (mserp) - with a S in the end of rates. <br>
Map the following values:
- Conversion factor -> Conversion Factor - from Currency Pairs
- Exchange Rate -> Conversion rate - from Get Exchange Rate
- Exchange rate type ->Exchange rate type - from Currency Pairs
- From Currency -> From Currency - from Currency Pairs
- To Currency -> To Currency - from Currency Pairs
<br><br>

<img width="910" height="725" alt="image" src="https://github.com/user-attachments/assets/8c66f3d1-f74c-4054-9629-fd0906d04df3" /> <br><br>

Now Press "Show advanced options" <br><br>
<img width="650" height="666" alt="image" src="https://github.com/user-attachments/assets/32bd0db4-1172-4d07-9d0d-e4f9757f3a98" /> <br><br>

Now Press "Show advanced options" <br>
Press the value for Start Date <br>
Press expressions <br>
And paste: getFutureTime(1, 'Day', 'D') in the FX field <br>
Press Ok <br> <br>
<img width="888" height="800" alt="image" src="https://github.com/user-attachments/assets/7facac06-f091-443b-ac6a-b48e11754909" /> <br><br>
<img width="562" height="827" alt="image" src="https://github.com/user-attachments/assets/bec56d51-f9b3-4e10-8696-0da14e67cb9f" /> <br><br>

This tells it that the start date of the exchange rate should be tomorrow. <br>

Press save <br><br>


Now it's time to test it! <br>
Press Test in the upper right corner<br>
Select Manual and press Test <br>
Press run flow and done <br><br>

By returning to the main page of the flow, you can view how your run has executed.<br>
When there are errors, you can access a specific run and read the errors by clicking on the time for it <br><br>

<img width="1108" height="556" alt="image" src="https://github.com/user-attachments/assets/8dc3d54a-9ef6-4140-b597-05ea83dcd746" /> <br><br>
<img width="1913" height="658" alt="image" src="https://github.com/user-attachments/assets/3c1fcceb-f056-4c64-a0c6-9aa4329990fb" />  <br><br>

But if you had a successful run or at least the majority of your runs were successful, Open F&O, search for "Currency Exchange Rates"<br><br>

<img width="492" height="507" alt="image" src="https://github.com/user-attachments/assets/a39ac866-6081-4202-9971-df767d3bc142" /><br><br>

And check if your updated rates are there! <br>
You can check between different exchange rate types if you want as well <br><br>

<img width="974" height="807" alt="image" src="https://github.com/user-attachments/assets/15b5123f-993b-4c62-81dc-1de9a842fb23" /><br><br>








































































































