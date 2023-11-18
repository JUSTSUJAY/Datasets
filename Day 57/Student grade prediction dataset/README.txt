*****************************************************************************
***********************      Directory Structure     ************************
*****************************************************************************

The data is provided in two formats (CSV and JSON) and stored in folders. 
The root folder contains 3 sub-folders labelled `original', `train_validate' and `test'.
Their content are as follows:
original: contains the full dataset in CSV and JSON formats
train_validate: contains two sub folders namely `csv' and `json'. The content of each is as follows
	6 files each containing training/validation dataset. 
	The `none.csv' contains imbalanced dataset 
	The rest contains balanced dataset oversampled with relevant SMOTE variation 
test: contains the testing dataset in CSV and JSON formats

*****************************************************************************
***********************       Data Description       ************************
*****************************************************************************

The original data contains 160 instances belonging to two classes (`pass' = 136 and `fail' = 24).
Each instance is made up of 19 features plus the class label
8 of the features represent students' online behaviour including bio information retrieved from VLE
11 of the features represent students' neighbourhood influence retrieved from Office for Students database
Full description of each feature is provided below:

****************************************************************************
*******************       Behaviour Features      **************************
****************************************************************************

Gender: Student gender classification (male = 0 , female = 1)
Age: Student age at week 6 of semester
Logins: count of module area logins
T-Engagement: Total hours spent in module area
P-Engagement: Percentage of average total hours spent in module area
Presence: Count of presence in compulsory learning sessions
Absence: Count of absence in compulsory learning sessions
P-Attendance: Percentage of compulsory learning sessions attended


****************************************************************************
****************      Neighbourhood Features        ************************
****************************************************************************

Home/Alt Address: If student attends from home (1) or alternative address (0)
Uni Distance: Distance between term-time address and campus
POLAR4: Current area classification of HE participation 
POLAR3: Old area classification of HE participation 
01-Adult HE: Adult proportion with HE qualification in area (2001 census)
11-Adult HE: Adult proportion with HE qualification in area (2011 census)
TUNDRA MSOA: HE participation rates of pupils from state school by MSOA
TUNDRA LSOA: HE participation rates of pupils from state school by LSOA
GCSE Gap: Observed vs. expected GCSE attainment by area
E-GCSE Gap: Observed vs. expected GCSE attainment by area and ethnicity
Uni Connect: Areas where POLAR3 = 1 and GCSE Gap = 1 or 2


****************************************************************************
**************************      Class Label        *************************
****************************************************************************

Class Label: Indicates whether student failed (1) or passed (0) the module 

[Note]
	(a) The Uni Distance feature was calculated using pgeocode python library. 
	(b) The POLAR, Adult HE, TUNDRA & GCSE Gap features were assigned 0 if postcode was coded as follows on the OfS database: 
		A: unsafe for measurement; 
		B: non-geographic; 
		R: Removed; 
		U: outside of England; 
		M or L: too few pupils for analysis.