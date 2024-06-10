# Instructional Design Template

This template is designed to assist in the development of training materials for the United States Army. The structure is based on the Experiential Learning Model (ELM) and the TRADOC Pamphlets for Course Development.

To learn more about using git and markdown for unit training, see the [Enhancing Unit Training with Git and Markdown](Git-For_Unit_Training.md) document.

Reference to the following Doctrine from [TRADOC Administrative Publications](https://adminpubs.tradoc.army.mil/pamphlets.html):
- TP 350-70-1
- TP 350-70-3
- TP 350-70-7
- TP 350-70-9
- TP 350-70-12
- TP 350-70-13
- TP 350-70-14
- TP 380-10 (Foreign Disclosure Pamphlet)

And ATP 5-19, Risk Management, 14 April 2014

## Download Template
1. **Graphical Option**: Use the Download Button Above.
2. **Terminal Option (Recommended)** to keep the template updated:
   ```BASH
   git clone https://github.com/irregularchat/template-instructional-design.git
   ```

## Update Template
Navigate inside the directory `poi-development` and execute the following command:
   ```BASH
   git pull
   ```

## For Developers
1. **Read the Developer Guide**: Start with [Developer Guide.md](/Development-Training_Name/Developer%20Guide.md).
2. **Review the Developer Workbook**: Familiarize yourself with [Developer_Workbook.xlsx](/Development-Training_Name/Developer_Workbook.xlsx).
3. **Start with Analysis**: Begin by defining the problem statement in [1-Analysis/1.ProblemStatement.md](/Development-Training_Name/Development-Training_Name/1-Analysis/1.ProblemStatement.md).
4. **Follow the Development Process**:
   - Complete the DOTMLPF analysis in [2.DOTMLPF.md](/Development-Training_Name/Development-Training_Name/1-Analysis/2-Task_Analysis/2.DOTMLPF.md).
   - Continue through task analysis, individual task analysis, DIF, ITA, SKM, performance measures, and TAP.

## For Instructors
1. **Read the Developer Guide**: Start with [Developer Guide.md](/Development-Training_Name/Developer%20Guide.md) to understand the development process.
2. **Review the Course Materials**:
   - Find the lesson plans and audio-visual content in the `4-Implement` directory.
   - Set up the training area according to the provided instructions in [Environment_Setup.md](/Development-Training_Name/Development-Training_Name/4-Implement/POI-Course_Name/Classroom_Setup/Environment_Setup.md).
   - Use the course syllabus and evaluation materials to guide the training process.
   - Example starting points:
     - [Course_Syllabus-POI-NAME.md](/Development-Training_Name/Development-Training_Name/4-Implement/POI-Course_Name/Course_Syllabus-POI-NAME.md)
     - [Instructor_Evaluation](/Development-Training_Name/Development-Training_Name/4-Implement/POI-Course_Name/Evaluation/Instructor_Evaluation)
     - [Training_Evaulation_and_Outlines_(TE&O).md](/Development-Training_Name/Development-Training_Name/4-Implement/POI-Course_Name/Evaluation/Training_Evaulation_and_Outlines_(TE&O).md)

### ELM
Training is designed primarily based on the Experiential Learning Model (ELM), taught at SWCS Course Faculty Course, and is a private sector standard.
 
If you have not been to the SWCS Course Faculty Course yet, study the following content:
- [Gagne's Nine Events of Instruction](https://youtu.be/-31fCUQ2htU)
### Academic Hour
50 minutes is an “hour” to allow students to take a 10-minute break or two 5-minute breaks. 
### Templates
Templates can be notes or entire folders. Duplicate templates as needed. 
### Comments
Comments are between percent symbols (\%%) and may describe. %%This is an inline comment%%

1. Why something is included, excluded, or modified 
2. How to properly use a section
%%This is a comment which... 

...is...
Comments can be single-line or multi-line%%
### Tags
#Knowledge, #Skills, #Resources, and #SupportingTasks should be added as tags to allow for quick sorting and linking

### NOTES
NOTE is used when an instructor is supposed to perform an action or deliver instruction to students. 

### Links
Pages, Directories, and Files can be linked directly or using relative path formatting. Adding an "!" will embed the page when using obsidian.
![Linked Item Name](/Development-Training_Name/)
or 
[Linked Item Name](/Development-Training_Name/)


### Paraphrasing
> Quote Brackets are used to show the instructor what needs to be paraphrased; a note will also provide this guidance


### Verbatim Quotes and Code
```md
Code Blocks are used for code 
Code Blocks are also used for verbatim requirements, which should not be paraphrased. The code block allows an instructor to notice quickly and to copy if needed.
```

### Spacing and New Lines

To Create New Lines, especially inside a table - use \<br\>, which will create a line break and continue typing. 

Creating a Line Break with a Line can help when sorting content. Use three (3) - in a single line to create a line break such as this:

### Moving to Slides
`##### SLIDE`  should be used to show movement to a new slide. This will allow collapsing and expanding slide instructions to be represented on the table of contents.

---

Spacing and newlines can cause differences in how Obsidian renders markdown. It is essential to include a new line after a "---" line break for proper rendering. 
--- 

## For Instructors and Students: Creating Issues
1. **Identify the Section**: Clearly identify the section of the training material that requires attention.
2. **Create an Issue**: Use the GitHub issue tracker to create a new issue.
   - **Title**: Issue with [Specific Section Name]
   - **Description**: Describe the issue in detail. Include any relevant information such as discrepancies, errors, or suggestions for improvement.
   - **Labels**: Apply relevant labels such as "bug", "enhancement", or "question".

## Background of Process and Format
This structure was developed after over a year of course development and instruction, with TRADOC Doctrine and the SWCS Course Developer Course referenced.
## How to Use This Notebook 
### Obsidian 
This markdown structure is best when used with [Obsidian](https://obsidian.md/) 

To expand or collapse sections/headers in a note Top Menu > Insert > {"Fold" or “Unfold”}  or configure a keyboard shortcut using the app preferences

## Troubleshooting
### sed on MacOS
- **Problem**: sed for Mac is missing some options which limit cross-compatibility when replacing a string.
- **Solution**: Install gnu-sed and map the PATH as needed.
   ```BASH
   brew install gnu-sed
   ```

### Replace a string in all documents
- **Solution**:
   ```BASH
   grep -RiIl 'Original_String';sleep 5;grep -RiIl 'Original_String' | xargs sed -i 's/Original_String/Replacement_New_String/g'
   ```

### Run Git Commands on Multiple Directories
- **Solution**:
   ```BASH
   find . -name .git -print -execdir git pull \;
   ```

