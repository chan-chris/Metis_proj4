## A Psychoanalysis of George Costanza using NLP
Readme.md

**Date:**
02/19/2021

**Description:**<br>
The purpose of this project was to perform topic modeling and sentiment analysis on the TV show Seinfeld, specifically on one of the main characters, George Costanza.
<br>
<br>
**Data:**<br>
The data I used was publicly avaialble on Kaggle:<br>
https://www.kaggle.com/thec03u5/seinfeld-chronicles
These files contained the transcripts for all 9 seasons (173 episodes) of the Seinfeld show. Each 'document' was a character's line per episode.<br>
For sentiment/emotion analysis, I used the NRC word-emotion association lexicon which is also publicly available and widely used in research:<br>
http://web.stanford.edu/class/cs124/NRC-emotion-lexicon-wordlevel-alphabetized-v0.92.txt
<br>
<br>
**Features and Target Variables:**<br>
Given this was an unsupervised learning analysis, there was no target feature. The data used was text data and general processes included the following:
<br>
Data cleaning and pre-processing:
	. count vectorize
	. lemmatize
	. EDA 
	. topic modeling
	. sentiment/emotion analysis  
<br>
**Programs:**<br>
This analysis was very exploratory in nature therefore programs journey through different approaches for analysis, some of which was not used in the final presentation. The primary program is 03_seinfeld_costanza.ipynb. as this contained much of the content found in the final presentation. A brief explanation of the programs are as follows:
<br>
<br>
**. 01_seinfeld_all_chars.ipynb**<br>
	. This program looks at all lines from all characters of the tv scripts. The idea was to try and glean topics of the show based on an 'episode' as a single document. <br>
	. Primary visuals used from this program are for total line counts per character across seasons as well as total mentions of character names across seasons<br>
	. The topic models did not yield very distinctive themes. This could be due to the resolution of the documents being parsed at the episode level.<br> 
    <br>
**. 02_seinfeld_main_chars.ipynb**<br>
	. This program attempted to analyze the 4 main characters only (Jerry, George, Elaine, Kramer). I took a similar approach as in the previous program.<br>
	. Again topic modeling did not yield the results I was hoping for and therefore I decided to focus on one character in the latter program<br>
	. No visuals from this program were used in the final presentation<br>
    <br>
**. 03_seinfeld_costanza.ipynb**<br>
	. This was the primary program of analysis and presentation.<br>
	. Data cleaning and pre-processing were used and then filtered down to the character George Costanza's lines only. Each document was an aggregate of George's lines per episode<br>
	. After different iterations of models, I chose a NMF Topic model which yielded 4 main topics:<br>
			. Dating, relationships, sex<br>
			. Episodes focusing on outings and events<br>
			. Jobs, occupation, ideas, schemes<br>
			. Family, Friends, food<br>
	. Sentiment / Emotion analysis<br>
			. Using the NRC emotion lexicon I flagged each word where that was identified as one of 8 emotions or positive or negative sentiments<br>
	. Visualizations include:<br>
		. frequency of emotion-specific words across all seasons<br>
		. pairing of the distribution of emotions/sentiment by topic<br>
		. word clouds for pos/neg sentiment<br>
<br>
**Summary:**<br>
<br>
The final analysis looks at each of George's 10 emotional states/sentiments and then looks at the distribution of the topics within each emotion. The top 10% percent of episodes that contained the highest emotional scores were extracted to create the charts portraying the intersection of emotion and topic. For example, if looking at the emotion "anger", of the 173 episodes I would take the top 15-20 episodes that had the highest "anger" scores. Using this subset of text I would glean which topics were most associated with those episodes.<br>
<br>
The main takeaway of the analysis is that the character of George Costanza is divided in terms of what brings out strong emotions. For example, dating and relationships bring about the most anger AND joy out of George (literally a love/hate relationship with love).<br>
<br>
It was eye-opening to see that his character increases in Positive sentiment over the seasons whereas his negative sentiment stayed flat. This may not be obvious at first glance but perhaps looking at the later seasons reveal George's more upbeat nature - perhaps (sadly unsuprisingly) after his fiance Susan dies and he is free from commitment. <br>
<br>
Another interesting find is that his negative sentiment may largely be related to his family history and/or interactions. We know his relationship with his parents is often portrayed as dysfunctional to say the least. This stands out more having looked at the distributions of each emotion over the 4 topics George's life revolves around.<br>
<br>
Lastly, we compare postive and negative sentiment by looking at word clouds. These reveal some overlap in characters names that could be associated with George's overall sentiment. His mother stands out as a person who brings negative sentiment. Elaine stands out as a person who brings more positive sentiment.