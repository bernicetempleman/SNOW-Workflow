# SNOW-Workflow

- Workflow is a virtual representation of tasks consisting of connected steps planned out in a sequential manner.

- The Graphical Workflow engine automates multi-step processes. Each workflow has a sequence of activities, such as generating records or running scripts, and transitions between them based on conditions.

- The workflow starts when a triggering event occurs. Common triggers include a record being inserted into a specific table, or a particular field in a table being set to a specified value. For example, you might create a workflow that runs whenever a user requests approval for an item they want to order from the catalog. 

- When an activity completes, the workflow transitions to next activity. An activity might have several different possible transitions to various activities, depending on the outcome of the activity. Continuing the example above, if the user's request is approved, the activity might transition to an activity that notifies someone to order the item; if the user's request is denied, the activity might transition to notifying the user that their request has been denied.

## Graphical workflow editor
The graphical Workflow Editor represents workflows visually as a type of flowchart. It shows activities as boxes labelled with information about that activity and transitions from one activity to the next as lines connecting the boxes.

For each step in the workflow:

1) An activity is processed; the behavior determined by the activity occurs.
2) When the action completes, the workflow checks each of the activity's conditions.
3) For each matching condition, the workflow follows the transition to the next activity.


When the workflow runs out of activities, the workflow is complete.
Is an interface for creating and modifying workflows by arranging and connecting activities to processes

Activities can be added, removed, or rearranged
                                 
Transitions can be drawn or changed, and the workflow powers the process as defined visually

- Note: The graphical workflow engine automates multiple-step processes. Each workflow generates a sequence of activities, for example: generating records or running scripts and the transitions between them based on conditions. Notification activities allow workflows to notify users of events that occur during the workflow

## Workflow Activities
A workflow activity contains instructions that are processed by the workflow.
Activities can include running scripts, manipulating records, waiting for a set period of time, or logging an event. Workflow conditions determine whether or not the activity is performed. Activities can be added, removed, or rearranged. Transitions can be drawn between activities.
This is an activity that triggers a notification:
![image](https://user-images.githubusercontent.com/12488769/148686094-cbb8423d-15c4-4c45-98b8-2080afc1b302.png)


For more information on available activities and their behaviours, see https://docs.servicenow.com/bundle/kingston-servicenow-platform/page/administer/using-workflows/concept/c_WorkflowActivities.html

## Transitions
After the workflow condition is evaluated, the workflow transition determines which activity is performed when the workflow condition is met. 

This is a transition that always leads from the Change Approved script to the Change Task activity:

![image](https://user-images.githubusercontent.com/12488769/148686137-6b7bd53e-9be8-4322-b17a-de3745a67fe2.png)

## Exit Conditions
After a workflow activity is performed, the workflow condition is evaluated to determine which transition is activated.

The condition determines behaviour based on a change being approved or rejected:

Sample exit conditions:

![image](https://user-images.githubusercontent.com/12488769/148686167-e14c414d-0dbe-4c96-bf0c-ec2ba7014f36.png)

## Workflow example
During workflow editing or while an unpublished workflow is running, only the person who checked out the workflow can view the changes.
After a workflow is published, it is available to other users. The workflow moves through the process as defined in the Workflow Editor. The entire workflow is represented in one screen. For example, this is the Standard Change workflow:

Sample Change Workflow:

![image](https://user-images.githubusercontent.com/12488769/148686204-986d4275-7735-446e-80de-05dafe3513e4.png)

## Validating a workflow
You can manually validate a workflow from the workflow editor.

If validation is successful, the system updates the workflow version record to indicate the workflow has been validated and marks the record as updated by the user who ran the workflow.

Open the workflow to validate in the workflow editor. When the workflow is loaded, the workflow validator icon appears in the toolbar. 


![image](https://user-images.githubusercontent.com/12488769/148686224-8e70c5c0-ec43-447c-91cf-bb7661695e0f.png)

Click the validator icon to run a series of validation tests on the current workflow version and generate a report.

![image](https://user-images.githubusercontent.com/12488769/148686243-8a53b1ed-57fc-4c6d-80e9-7c101ce11c69.png)

## Cancelling a workflow
Cancelling a workflow stops the workflow from executing and sets the workflow context State to Cancelled. It attempts to stop the workflow gracefully by injecting a cancel command into the workflow engine.

To cancel an active workflow:

1. Navigate to Workflow > Active Contexts. 
2. Select a workflow context record. 
3. Select the Cancel related link. A confirmation window appears.

![image](https://user-images.githubusercontent.com/12488769/148686265-a13f7759-a332-4e35-a4f0-d2c3bf0b89c1.png)

4. The Wait for Cancel window appears. The workflow engine attempts to cancel the workflow gracefully.
![image](https://user-images.githubusercontent.com/12488769/148686277-ed19458d-3388-46a8-90b7-a37492b74a80.png)

![image](https://user-images.githubusercontent.com/12488769/148686281-1aeb6eb1-13a3-44f1-8faf-adc4dd17d552.png)

If the workflow does not respond to the cancel command, the Force Cancel window appears. 
![image](https://user-images.githubusercontent.com/12488769/148686291-6b652dcf-b3fd-4d66-af26-20da677f4169.png)

![image](https://user-images.githubusercontent.com/12488769/148686300-721b2b9f-5796-48bf-bb91-502d5bbe6a3a.png)

5. Click Force cancel to interrupt the thread the workflow is actively executing or click Continue waiting to continue waiting for the workflow to cancel gracefully.
![image](https://user-images.githubusercontent.com/12488769/148686307-5b07a426-dcb4-4eb8-b14b-e0c3f471d50d.png)

## Creating a workflow
To create a new workflow, navigate to Workflow > Workflow Editor and click New.

There are three major steps to creating a workflow:

 Defining Workflow Properties
 Adding Workflow Activities
 Publishing the Workflow
![image](https://user-images.githubusercontent.com/12488769/148686326-177d34c5-6256-48c0-8b78-689d8723a072.png)














