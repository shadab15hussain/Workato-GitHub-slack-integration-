# Workato-GitHub-slack-integration-
A sample workato project  to automate GitHub  to slack notification 
{
  ---

### 📦 `recipe.json`

```json
{
  "name": "GitHub to Slack Notifier",
  "trigger": {
    "type": "github.new_issue",
    "params": {
      "repo_owner": "{{env.GITHUB_REPO_OWNER}}",
      "repo_name": "{{env.GITHUB_REPO_NAME}}"
    }
  },
  "steps": [
    {
      "action": "slack.post_message",
      "params": {
        "channel": "{{env.SLACK_CHANNEL}}",
        "text": "🚨 *New GitHub Issue Created*\n*Title:* {{trigger.issue.title}}\n*URL:* {{trigger.issue.html_url}}"
      }
    }
  ]
}
