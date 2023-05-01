**Settings/Functions on the “Create View” Page**
- **UR-1** “Report View Name” → sets Report View displayname for the roles: FirmManager and Advisor.
  - UR-1.1 Text box
  - UR-1.2 Character limit = 255
  - UR-1.3 Validation: once user clicks outside of “Report View Name” textbox, validate displayname character count <= 256
	UR-1.3.1 If Fails validation, then display red border around text box
•	UR-2 Radio Icon “Report Type” component with options for Firm Report / Client Report → sets Report View viewcontext
•	UR-3 Radio Icon “Format” component with options for CSV / PDF/ XLS → sets Report View format
•	UR-4 Radio Icon “Orientation” component with options for Landscape/Portrait → sets Report View orientation
o	UR-4.1 IF ReportView format = PDF, then show Orientation component only for FirmManager.
o	UR-4.2 Else hide Orientation component
•	UR-5 Button: “Create View”
o	UR-5.1“Create View” is greyed out and not clickable unless:
	UR-5.1.1 displayname is not null
	UR-5.1.2 viewcontext is not null
	UR-5.1.3 format is not null
	UR-5.1.4 IF format = PDF, then orientation is null
o	UR-5.2 Upon click, attempts to create and save Report View object
	UR-5.2.1 Save Validation: upon save, validate that displayname must be unique within firm
•	UR-5.2.1.1 If Fails validation, then display red border around text box and prevent save
	UR-5.2.2 Save Validation: upon save, validate that displayname character count <=255
•	UR-5.2.2.1 If Fails validation, then display red border around text box and display message:
o	UR-5.3 Upon successful save by clicking Save button, takes you to Report Builder Page

| Requirements |  Bugs  |
|--------------|--------|
|See UR-1.2; See UR-1.3| Displayname character count <= 256 contradicts сharacter limit = 255|


