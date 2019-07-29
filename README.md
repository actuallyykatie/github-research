# Analysis of Newcomers Activity in Communicative Posts on GitHub
Research on newcomers activity in communicative posts on GitHub as a part of a project at HSE SPb :octocat:

---
## Plan
:telescope::clipboard::pencil: :chart_with_upwards_trend: :squirrel: :tada:

## Overview

The aim of this project is to investigate relations towards newcomers through sentiment analysis of comments they receive in issues and pull requests in repositories of top-10 open source projects by contributor count and top-10 fastest growing open source projects based on [The State of the Octoverse 2018](https://octoverse.github.com/projects#repositories) report by GitHub. By applying sentiment analysis we focus on differences between reactions to contributions of ‘old’ and ‘new’ developers, and find that while the majority of comments is rated as neutral, the amount of negativity is slightly higher for newcomers.

## Data
The data was collected using PyGitHub Python library and scraping which is allowed for research purposes ([GitHub Terms of Service](https://help.github.com/en/articles/github-terms-of-service#5-scraping)). 

### Repositories
Dataset with information **about repositories**.  
Date: 28/04/2019  
1. **full_name** - full name of the repository *(owner/title)*  
2. **name** - title of repository  
3. **description**  - description 
4. **owner** - owner  
5. **language** - programming languages used
6. **forks_count** - number of forks
7. **stargazers_count** - number of stargazers  
8. **watchers_count** - number of watchers  
9. **open_issues_count** - number of open issues  
10. **topics** - topics *(i.e. tags)*  
11. **contributors** - list of contributors 


### Issues & Pull Requests (communicative posts)
Data **about comments** for issues and pull requests.  
Date: 25/04/2019 to 30/04/2019

1. **repo_author** - Repository author *(company name)*  
2. **repo_title** - Repository title  
3. **issue_title** - Issue/PR title  
4. **issue_number** - Issue number   
5. **state** - State  
6. **rev_or_ass** - Reviewers/Assignees  
7. **labels** - Labels  
8. **created_at** - Created at  
9. **num_of_participants** - Number of participants  
10. **comment_number** - Issue's comment number *(i.e. 1st, 2nd..;c omment_number==1 --> issue body)*  
11. **reactions** - Reactions  
12. **comment_date** - date of comment  
13. **contributor** - user's status. True/False. 
14. **author** - user's status. True/False. 
15. **member** - user's status. True/False.
16. **collaborator** - user's status. True/False.  
17. **login** - commentator's login  
18. **closed_by** - who closed an issue/PR *(if so)*  
20. **closed_at** - Closed at  
21. **comment_body** - text of comment   



## Methods

- defined newcomer as a person who created less than 3 issues/PRs to the repository;
- dictionary-based sentiment analysis using VADER;   
- the original VADER lexicon was updated with words with specific meaning at GitHub, such as “bug”, “ship it”, “LGTM”. The selected words were scored by 5 individuals independently and then averaged.


Examples of sentiments scores for comments.

Sentences | Negative | Neutral | Positive | Compound
----------|----------|---------|----------|---------
this is a 🐛 | 0.429 | 0.571 | 0.000  | -0.128
Yes - looks like 💩 with the extra line  | 0.197 | 0.461 | 0.342 | 0.296
ship it!!! | 0.000 | 0.170 | 0.830 | 0.707
If you are interested in working on this issue please feel free to create a PR :)  | 0.000 | 0.451 | 0.549 | 0.908
Must have been something messed up on the infill but reprint looks good and essentially indistinguishable from current LINEAR_ADV code #shipit ;) | 0.054 | 0.573 | 0.373 | 0.900
Fault isolation is not about scalability but isolating resource consumption. For example what happens in one function eats up all threads or memory? Or if one function can cause the whole machine to be crushed? | 0.195 | 0.805 | 0.000 | -0.776



## Conclusion
In this work, we analyzed the relationship towards newcomers by applying sentiment analysis to comments they receive in issues and pull requests. Both tops of repositories have a high percentage of users who contributed less than 3 times. The majority of comments was rated as neutral, however, the amount of negativity appeared to be slightly higher for newcomers. The distribution of compound scores between newcomers and non-newcomers in top projects by unique contributors count appeared to be higher than for newcomers and non-newcomers within fastest-growing projects.

Overall, it still remains a question who should be considered as a newcomer, and whether these users are active in other repositories. Thus, it will be good to examine users’ overall activity outside the selected repositories, check whether and how it differs depending on the skills required in further research. The 'developers' context should be examined more clearly and other lexicons may be used in order to receive sentiment scores. 


