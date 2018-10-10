# nus-scantron-mrq

Author: Min-Yen KAN <kanmy@comp.nus.edu.sg>

Scantron Scantools Application and Conversion Profile for Multiple Response Questions for the School of Computing's Scantron Form

This file documents how to use the standard School of Computing Multiple Choice Question (50 Question) worksheet to be used for multiple response questions; i.e. "mark all responses that apply", as opposed to the simple "mark one only" multiple choice questions).

This software is installed and usable on the MCQ machine in the Equipment Room in SoC COM2 #02-63.  If using it elsewhere you will need the two files in the root directory of this repository:

* [Z556.SDS](../master/Z556.SDS) goes in `C:\Program Files (x86)\Scantron\ScanTools Plus\Applications`
* [CS3244.$CP](../master/CS3244.$CP) goes in `C:\Program Files (x86)\Scantron\ScanTools Plus\Profiles`

The latter file may have been renamed on the computer to `556.$CP` or similar.

## Steps for using the application

1. First, launch the application.
   ![Scantools Icon](https://github.com/knmnyn/nus-scantron-mrq/blob/master/images/scantool.jpg?raw=true "Scantool Icon")
2. Select the appropriate application and datafile.  The application is "556 MCQ 50 (KanMY)".  You may have to add a new datafile, or if you use an existing datafile, you may have to delete it so that compatibility problems don't arise (say if you are re-using the same file from last semester).
   ![New Datafile](https://github.com/knmnyn/nus-scantron-mrq/blob/master/images/newdf.jpg?raw=true "New Datafile")
3. Load in your MCQ 50 forms with the reading barcode facing the input of the machine (that is, load the paper sideways).  In my experience, loading small batches is good, as the machine can jam fairly easily.  Don't feed crumpled papers; either do these again on another MCQ sheet on behalf of the original, or hand-enter them later (since it takes longer to fill in a new form than typing the results in for those that got stuck).  After loading ... (wait for it ... wait for it) ... press "Scan"!
   ![Load the Scanner](https://github.com/knmnyn/nus-scantron-mrq/blob/master/images/scanner.jpg?raw=true "Load the Scanner")
4. After scanning, your files will appear in the destination directory (which in this computer at the Equipment Room in SoC COM2 #02-63, is `D:\SFW\results\`.
   ![Datafile](https://github.com/knmnyn/nus-scantron-mrq/blob/master/images/datafile.jpg?raw=true "Datafile")
5. After it completes, you can load in your CSV into Excel.  The results should look like this, with a column for the Student ID, and columns for each mark all "MA" question 1 through 50.  Each entry is "left-justified" such that the question will have _nil_ (no response) or a substring of "ABCDE" in the entry.
   ![CSV in Excel](https://github.com/knmnyn/nus-scantron-mrq/blob/master/images/csvinxls.jpg?raw=true "CSV in Excel")

6. I suggest that you convert the CSV file into an Excel spreadsheet so that you can do the scoring more comprehensively in the spreadsheet directly.
7. For marks safety, I also suggest that you securely delete the marks file from your scan after you leave.
8. For MCQ (i.e., "mark one choice" vs. this "mark all responses"), please reset the application to the "555" application, scoring profile and conversion application.  The "555" MCQ application has scoring pre-built against a key, whereas in this application, I have not yet set a scoring mechanism and prefer to do the scoring separately.

## In-Frequently Asked Questions (iFAQ)

1. Can you use Multiple Choice questions on the form?  Yes.  The form allows you to do both.

2. Partial credits.  Wai Kay suggests:

> To me, an option is correctly answered if it is supposed to be shaded and student shades it, or it is supposed to be unshaded and student did not shade it.  
> 
> Thus the marking scheme I use is:
> * 3 marks for all 5 correct 
> * 2 marks for 4 correct
> * 1 mark for 3 correct
> * 0 marks otherwise.
>
> This will give a random chance of around 25%, which is slightly more than 5 option MCQ. But less than 50% if taken as a set of T/F questions.

3. Sample instructions.  I suggest:

  ![Sample Instructions](https://github.com/knmnyn/nus-scantron-mrq/blob/master/images/s-instr.png?raw=true "Sample Instructions")
   
4. None of the above marking: Do we need to worry about having an option for "None of the Above"?  Do we avoid the anomaly that a student who didn't have time to answer some questions still earning some marks for those unanswered questions.

> I wouldn't be too concerned about this. No students will leave blanks in an MCQ if they run out of time. They would just randomly shade an option. Having MRQ with option E as "None of the above" will just result in this happening, and you would have removed 1 of the 32 possible combinations. With MRQ they would randomly shade 2 or 3 and hope for the best

> True. To add,
> * Using E is 'None of the above' actually makes it a 4-choice question, reducing legit combinations from 32 to 16?
> * Yes, students do random shading for MCQ but with MRQ there is no need to randomly shade anything, as an unanswered question is 50% correct already (provided roughly half the options are 'false' options). Random shading does not improve those odds.

## History

I cloned the original 555 application that works for the same 50 MCQ response sheet and renamed it 556 to test out how it might work, hence the ID "556".
