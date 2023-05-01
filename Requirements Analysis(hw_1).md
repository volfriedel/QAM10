First of all, I decided to number the points in order to improve the traceability of the requirements.

**Settings/Functions on the “Create View” Page**
- **UR-1** “Report View Name” → sets Report View displayname for the roles: FirmManager and Advisor.
  - **UR-1.1** Text box
  - **UR-1.2** Character limit = 255
  - **UR-1.3** Validation: once user clicks outside of “Report View Name” textbox, validate displayname character count <= 256
    - **UR-1.3.1** If Fails validation, then display red border around text box
- **UR-2** Radio Icon “Report Type” component with options for Firm Report / Client Report → sets Report View viewcontext
- **UR-3** Radio Icon “Format” component with options for CSV / PDF/ XLS → sets Report View format
- **UR-4** Radio Icon “Orientation” component with options for Landscape/Portrait → sets Report View orientation
  - **UR-4.1** IF ReportView format = PDF, then show Orientation component only for FirmManager.
  - **UR-4.2** Else hide Orientation component
- **UR-5** Button: “Create View”
  - **UR-5.1** “Create View” is greyed out and not clickable unless:
    - **UR-5.1.1** displayname is not null
    - **UR-5.1.2** viewcontext is not null
    - **UR-5.1.3** format is not null
    - **UR-5.1.4** IF format = PDF, then orientation is null
  - **UR-5.2** Upon click, attempts to create and save Report View object
    - **UR-5.2.1** Save Validation: upon save, validate that displayname must be unique within firm
      - **UR-5.2.1.1** If Fails validation, then display red border around text box and prevent save
    - **UR-5.2.2** Save Validation: upon save, validate that displayname character count <=255
      - **UR-5.2.2.1** If Fails validation, then display red border around text box and display message:
  - **UR-5.3** Upon successful save by clicking Save button, takes you to Report Builder Page

| Requirements |  Bugs  |
|--------------|--------|
|See UR-1.2; See UR-1.3| Displayname character count <= 256 contradicts сharacter limit = 255|
|See UR-3; See design mockup|Missing option for XLS on the design mockup|
|See UR-5; See design mockup|Missing Button: “Create View” on the design mockup |
|See UR-4.1; See UR-5.1.4| Orientation can’t be null. I suppose in the case of choosing PDF, the orientation should take one of the options on default. Also, in case when user is FirmManager, he have to choose orientation, even if he chose PDF format.|
|See UR-1.3; See UR-5.2.2|Double validation of character count|
|See UR-5.3|Missing Save button on the design mockup (or meaning of Save button)|
|See UR-1.3.1; See UR-5.2.2.1|Double display red border around text box|
|See design mockup|Missing Button: “Next” in requirements (or meaning of button “Next”)|
|See UR-5.2.2.1|What message|


Notes:
1.	To my mind, better use Radio Button instead of Radio Icon cause it the most common and understandable concept.
2.	Does the user's role affect the completion of the form, except in the case of format selection?
3.	Always Offer a Default Radio Button Selection is a good practice. 
>One of the 10 heuristics of UI design says that users should be able to undo (and redo) their actions. This means enabling people to set a UI control back to its original state. In case of radio buttons this means that radio buttons should always have exactly one option pre-selected. Select the safest and most secure option (to prevent data loss). [source](https://uxplanet.org/radio-buttons-ux-design-588e5c0a50dc)




