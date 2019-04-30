# Analysis of Newcomers Activity in Communicative Posts on GitHub
Research on newcomers activity in communicative posts on GitHub as a part of a project at HSE SPb. Currently in progress :octocat:

---
## Plan
:telescope::clipboard::pencil: :chart_with_upwards_trend: :squirrel: :tada:

## Overview
The aim of this project is to analyze communication between developers and newcomers in top-10 open source projects by contributor count and top-10 fastest growing open source projects based on [The State of the Octoverse 2018](https://octoverse.github.com/projects#repositories) report by GitHub using sentiment analysis. We investigate whether new developers face more negativity, whether it prevents them from further contribution into projects, and if so, how it differs depending on the type of repository.

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
9. **closed_at** - Who closed the issue/PR and when *(if so)*
10. **num_of_participants** - Number of participants
11. **comments** - Comments. Includes the user's status *(collaborator/author/owner/member)*, user login, date, comment
12. **reactions** - Reactions





