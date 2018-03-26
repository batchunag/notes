#Get all statuses
http://your-site-here/rest/api/latest/status/
/rest/api/latest/status/{id}

#Get transitions for specific issue
/rest/api/2/issue/{issueIdOrKey}/transitions

/rest/api/2/project/{myProject/statuses

#new webhook
{
  "name": "my first webhook via rest",
  "url": "http://www.example.com/webhooks",
  "events": [
    "jira:issue_created",
    "jira:issue_updated"
  ],
  "jqlFilter": "Project = JRA AND resolution = Fixed",
  "excludeIssueDetails" : false
}