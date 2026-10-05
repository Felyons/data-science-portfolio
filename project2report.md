# Findings

A Democratic Republic by definition is a nation where the power rests with the people, who in turn elect leaders to represent them and make laws. (Smith, 2026)
The Government is split into 3 categories; Executive, Legislative, and Judicial. Elections are held every 2 years with the presidential taking place every four. The
models highlighted below were created to help with visualize the up coming midterms, focusing on the United States Senate. Senators do not have a term limit and go up for reelection every 6 years. The Senator currently in office is known as the Incumbent, as we approach the election its proper etiquette to announce that they will be vacting the seat creating what is know as a free seat. Much like the Presidential elections parties go through a primary process in which they decide on what candiate will make the ballot for the election. 

## Variable Process

When attempting to run for office the main thing a candidate has is their word. The stance in which they campaign on define them, attracting voters with common beliefs and sharing in their party platform. How do they spread their message? Advertising. The process of campaigning is not a cheap one, the ability for a candidate to properly portray themselves into the main stream comes from backing. Financial donations are a fundamental part of elections, the sheer amount of money one candidate can raise can reflect a life time of earnings.

Do campaign donations determine who will win once the ballots are counted?

The FEC, Federal Election Commission is responsible for tracking and reporting campaign finances. Using "Raising: by the numbers" [(FEC, 2026)](https://www.fec.gov/data/raising-bythenumbers/) I collected campaign finance data on Senate Elections in key battleground states for the upcoming midterms in North Carolina, Michigan, Texas, Georgia, New Hampshire. In order to supply proper training data the years 2020, 2014, and 2008 were collected.

<img style="width: auto; max-width: 100%;" alt="image" src="https://github.com/user-attachments/assets/ae023494-3d5a-4ae1-a08a-2a7b4023e9fa" />
*DataFrame was crafted by hand. AI assited in automation of variable assignments, model ChatGPT Free*
*179 x 8*

Above is the constructed DataFrame used to train a Decision Tree machine learning model to understand the true weight in which financial contributions carry during
campaigning. For the sake of visual understanding the columns "candidate_id" and "candidate_name" are included, not considered during training.

### Variable Definition

* total_disbursements: The total amount of money spent by the candidate during campaign.
* party_nom: If the candidate was selected by associated party to make it on the ballot
* GOAL VARIABLE won_term: Did they win.
* pres_party: During the year in which the election takes place does the candidate align with the same party as the sitting president
* state_party: in terms of US Senate Election voting only does the candidate align with historical voting outcomes.
* incumbent_challenge_full: A series of 3 one-hot encoded columns determining the status of the seat for upcoming election.

### Trained Model

<img style="width: auto; max-width: 100%;" alt="image" src="https://github.com/user-attachments/assets/a7a2bb27-ea32-41bc-a2ce-a6eced06f45f" />
*Model hand trained. Visual was assisted with AI, model ChatGPT Free*

- According to the model its understood that although finances do carry high weight for predicting a US Senate election it is not the strongest indicator. The best indicator for predicting the outcome of an election is incumbency. The fact that a Senator has served in that office creates the most impact on the outcome. Since a senator spends six years in office their base has a chance to witness the protentional real change in which the senator campaigned on. For an incumbent senator the model indicates one of the only challenges to their office is a Presidential election cycle. As defined earlier the "pres_praty" variable is used to determine whether a candidate is aligned with the sitting President. An important point to keep in consideration is "the president's party almost always loses ground in the midterm election following his victory" (Galston, 2025). This idea will play a crucial role in our upcoming midterms for Jeanne Shaheen (NH, D), John Cornyn (TX, R), and Jon Ossoff (GA, D). All senators are running as current incumbents but Senator Cornyn is Republican, he does benefit however from the traditional voting history in Texas. For Senator Ossoff who secured his seat in a runoff election in Georgia 2020 against the traditional voting standards holds a strong chance in secruing his seat for another term
- In Michigan and North Carolina both both are set as free set elections. Candidates Roy Cooper (NC, D) and Michael Whatley (NC, R): Abdul El-Sayed (MI, D) and Mike Rogers (MI, R) campaign in some of the most intense battle ground states for the 2026 midterms. North Carolina with a traditional Republican Senate seeing Senator Tillis relive his seat protentional stand to make a considerable pick up with Roy Cooper an ex NC governor running for the Democratic party. Michigan on the other hand a traditional Democractic state see Senator Peters relive his seat creating an opening for the Republican candidate Mike Rogers to make an impact.

<img width="752" height="362" alt="image" src="https://github.com/user-attachments/assets/6455f3f0-db94-43a7-a78a-7c9374cf3391" />

- This simple bar graph tracking candidates that received "party_nom" shows more evidence supporting our new findings. Even though a candidates raising efforts might have exceeded expectations, the established Senator has a strong hold on their seat. 

<img style="width: auto; max-width: 100%;" alt="image" src="https://github.com/user-attachments/assets/a4cbb30e-4403-4391-bd31-52ad6abbe7d1" />
<img style="width: auto; max-width: 100%;" alt="image" src="https://github.com/user-attachments/assets/33a6a095-e2dd-4c7b-962a-065b59e95f86" />

- Above is a linear regression model testing ```won_term ~ ``` for more support of our new findings. Immediately the model states weak correlation with an R^2 value of .453 and the p-value associated with log_disbursements(value corrected total_disbursements) exceeds the stated level of .05. However if looking at the model in terms of incumbency with a p-value of .000 supported by the party_nom p-value of .000 the previous stated importance of incumbency is once again supported.
- The QQ plot does the same. Visualizing a close grouping of residuals, as we reach the higher positive numbers we see the graph shift slightly from the normal distribution. I believe this occurs due to circumstances like the previously mentioned Senator Ossoff Georgia 2020 election as well as instances of extreme spending in open seat elections. 

## Conclusion

Elections are the defining factor of a functioning democracy. Attempting to understand all the factors behind one candidates success and anothers failure is 
something for researches to study for as long as we continue this process. However isolating a variable in which we hope to gain a deeper understanding of is possible. For the question "Does campaign financing determine who will win?" an assumption was draw that millions must have impact however after running the models described above a different outcomes seems to have arisen. The fact of incumbency, a senator having held a seat for a prior term in which they choose to run again almost completely denies any challenges regardless of the war chest their rival may possess. One factor does exist to slightly shift these predicted odds, the sitting President aligned party, as factor of democracy it seems that the America people will vote opposite for their elected senators regardless of President. 

Applying these ideas to the question of the 2026 midterms the model's tend to favor; 
- Roy Cooper(NC, D)
- Senator Jeanne Shaheen(NH, D)
- Senator John Cornyn(TX, R)
- Senator Jon Ossoff(GA, D
- Abdul El-Sayed(MI, D)

It is important to note that these are the conclusions of only the models described, for any model its limiting factors are the data on which it was trained 2020, 2014, 2008. Immediately if I choose to expand upon this project testing results until atleast 1996. The inclusion of all 50 states would be a minimum if usage of the model wished to be widespread. I believe that to find more support in the conclusion of incumbency running a new decision tree that finances are not included in is the best route, replacing with variables that state prior government service and potentially education background. 

[**Notebook**](Project2.ipynb) | [**CSV Download**](campaigncomp.zip) | [**Bibliography**](bibliography2.md)


