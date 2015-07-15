# AdmPdfInserterDesktop
Java desktop app for dynamically generating PDF decision letters and database insert

This application allows the Admissions office at the Havard School of Public Health to generate PDF decision letters into a file system and insert these letters into the back-end database.  For quality control, Admissions can first click one button of the desktop app to write these letters to a specified file system, where the documents may be reviewed; after validation, Admissions can click another button to insert the letters into the database.


Following the MVC framework, the code is divided into the following package diretories: controller, model, swing (for the view), and letters (for dynamically populating the templated letters with relevant data). The class Main sits ouside of these directories and initiates the application.

The controller package contains the following classes: ActionManager (the top-level controller class), BannerInsertListener (to insert decision letters into the database), ListBuildListener (to produce a list of applicants who received a final admissions decision but currently have no letter), LoginListener (for user authentication), SkipWriteFileListener (in case the letters need not be written, or rewritten, to the file system), WriteFileListener (to write the letters to the file system).


The letters package contains the following classes: AcceptDecisionPdfLetter (to generate an acceptance letter), DecisionPdfLetter (to provide data and methods needed for the different types of decision letters), DeferDecisionPdfLetter (to generate a deferred acceptance letter), PDFCreater (to retrieve the PDF decision letter as a byte array), RejectDecisionPdfLetter (to generate a rejection letter), WaitlistDecisionPdfLetter (to generate a waitlist letter),

The model package contains the class DataModel to store data that's needed across the application, at various stages of execution.

The swing package contains the following classes: AdmPdfInserterFrame (the top-level GUI component that initializes AdmPdfInserterPanel), AdmPdfInserterPanel (the top-level GUI container within AdmPdfInserterFrame), ApplicantListPanel (to display the list of applicants who need decision letters), ControlPanel (to provide controls for user interactions with the application), LoginPanel (the initial display for user authentication).
