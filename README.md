# Speaker Evaluation Statistics Report
When organizing events in which sessions are planned, it is important to gather feedback from participants in order to understand whether the interest and expectations of attendees have been met. Feedbacks are also useful to speakers, who can understand if the material prepared and the speech waere appreciated by attendees.

In order to collect all the feedbacks for each session, evaluation forms are often provided to attendees. The following one is the evaluation form used in [SQLSaturday #777 in Parma](https://www.sqlsaturday.com/777/eventhome.aspx):

<img src="feedback.png" width="400">

Here the meanings of Italian phrases:

| Italian | English |
| ----------- | ----------- |
| Titolo sessione | Session title |
| Quali erano le tue aspettative | What were your expectations | 
| Quanto è stato interessante | How interesting it was |
| Questo corso è stato utile | This course was useful |
| Come ti è sembrata l'esposizione | How the oral presentation was |
| Cosa ne pensi dello speaker (barra le qualità dello speaker) | What about the speaker (Check the speaker's qualities) |
| Divertente, Esperto, Oratore, Motivatore, Insegnante | Funny, Expert, Orator, Motivator, Teacher |
| Note | Notes |

At the end of the event, all the session evaluations are collected and registered in an Excel file.
Following a given Excel template, the R code provided in the Rmd ([R Markdown](https://rmarkdown.rstudio.com/articles_intro.html)) file generates a beautiful report about the statistics of feedbacks if [compiled in RStudio](https://kbroman.org/knitr_knutshell/pages/Rmarkdown.html#converting-r-markdown-to-html).


## Technical Details
The report generated by the Rmd file automatically adapts itself to customized sets of session and speaker's attributes used in the form. In order to correctly compile the report, you have to follow some guidelines you can find below.
### Excel File Structure
The Excel file used to collect the feedbacks has to have two sheets in the following order:
1. Speakers
2. Sessions

You can find an Excel file with the upon mentioned structure in this repository. It is used for the demo.

The *Speakers* sheet contains the following informations:
- Speaker name
- Session name
- Track name (usually sessions are organized in tracks to better address the attendees interest)
- Room capacity

The *sessions* sheet contains all the informations about the session evaluations:
- Speaker name
- { a set of session evaluations } (values between 1 and a max defined in the form, in our case 6)
- { a set of speaker evaluations } (values can be 1 or 0)
- Notes (optional)

The two aforementioned sets of variables have to be declared into the R code.

### Input Parameters in R Code
The input parameters to fill in the Rmd file are the following:
- *excel.full.path* (full path of the Excel file; giving only the filename with the extension, will get the file in the same folder of the Rmd file)
- *speaker.characteristcs* (in our case: "Expectation", "Interesting", "Useful", "OralPresentation")
- *speaker.qualities* (in our case: "IsFunny", "IsExpert", "IsOrator", "IsMotivator", "IsTeacher")
- *exists.notes* (flag that identifies the existence of the "Notes" variable)
- *characteristics.circular.barplot.txthjust* (vector for label adjustments in a barplot)
- *qualities.circular.barplot.txthjust* (vector for label adjustments in a barplot)
- *feedback.image.path* (full path of an optional image of the evaluation form)

### R Version Used
I developed the R script using the **3.4.3 version**. It is tested with success on 3.5.x version (using the updated library of *tidyverse*).

## Current Limitations
Actually the report has the following limitations:
- One speaker can deliver only one session

## Demo
You can find a fully functional HTML demo [here](https://lucazav.github.io/speaker-evaluation-statistics-demo)
