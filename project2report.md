# Findings

A Democratic Republic by definition is a nation where the power rests with the people, who in turn elect leaders to represent them and make laws. (Smith, 2026)
The Government is split into 3 categories; Executive, Legislative, and Judicial. Elections are held every 2 years with the presidential taking place every four. The
models highlighted below were created to help with visualize the up coming midterms, focusing on the United States Senate. Senators do not have a term limit and go up for reelection every 6 years. The Senator currently in office is known as the Incumbent, as we approach the election its proper etiquette to announce that they will be vacting the seat creating what is know as a free seat. Much like the Presidential elections parties go through a primary process in which they decide on what candiate will make the ballot for the election. 

## Variable Process

When attempting to run for office the main thing a candidate has is their word. The stance in which they campaign on define them, attracting voters with common beliefs and sharing in their party platform. How do they spread their message? Advertising. The process of campaigning is not a cheap one, the ability for a candidate to properly portray themselves into the main stream comes from backing. Financial donations are a fundamental part of elections, the sheer amount of money one candidate can raise can reflect a life time of earnings.

Do campaign donations determine who will win once the ballots are counted?

The FEC, Federal Election Commission is responsible for tracking and reporting campaign finances. Using "Raising: by the numbers" [(FEC, 2026)](https://www.fec.gov/data/raising-bythenumbers/) I collected campaign finance data on Senate Elections in key battleground states for the upcoming midterms in North Carolina, Michigan, Texas, Georgia, New Hampshire. In order to supply proper training data the years 2020, 2014, and 2008 were collected.

<img style="width: auto; max-width: 100%;" alt="image" src="https://github.com/user-attachments/assets/ae023494-3d5a-4ae1-a08a-2a7b4023e9fa" />
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

- According to the model its understood that although finances do carry high weight for predicting a US Senate election it is not the strongest indicator. The best indicator for predicting the outcome of an election is incumbency. The fact that a Senator has served in that office creates the most impact on the outcome. Since a senator spends six years in office their base has a chance to witness the protentional real change in which the senator campaigned on. For an incumbent senator the models seems to indicate one of the only challenges to their office is a Presidential election cycle. As defined earlier the "pres_praty" variable is used to determine whether a candidate is aligned with the sitting President. 

<img width="752" height="362" alt="image" src="https://github.com/user-attachments/assets/6455f3f0-db94-43a7-a78a-7c9374cf3391" />

- This simple bar graph tracking only candidates that received "party_nom" shows more visual evidence supporting our new findings. Even though a candidates raising efforts might have exceeded expectations, the established Senator has a strong hold on their seat. "




