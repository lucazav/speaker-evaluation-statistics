# Speaker Evaluation Statistics Report
When organizing events in which sessions are planned, it is important to gather feedback from participants in order to understand whether the interest and expectations of attendees have been met. Feedbacks are also useful to speakers, who can understand if the material prepared and the speech waere appreciated by attendees.

In order to collect all the feedbacks for each session, evaluation forms are often provided to attendees. An example of evaluation form to be compiled is this one:

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

## Demo
You can find a fully functional HTML demo [here](https://lucazav.github.io/speaker-evaluation-statistics-demo)

## Technical Details
