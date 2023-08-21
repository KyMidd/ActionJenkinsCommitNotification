# ActionJenkinsCommitNotification

This Action is intended to notify Jenkins when a change has ocurred within a repo. Jenkins operates on a notification model, not a polling model, so this type of action is necessary to trigger a Jenkins build.

```yaml
name: Jenkins Commit Notification
on: 
  push:
    branches:
      - develop
      - master

jobs:
  jenkins_monitor:
    runs-on: ubuntu-latest
    
    steps:
      - name: Jenkins Commit Notification
        id: jenkins_commit_notification
        uses: kymidd/ActionJenkinsCommitNotification@master # Or pin to hash
        with:
          jenkins-username: "${{ secrets.JENKINS_USERNAME }}"
          jenkins-api-token: "${{ secrets.JENKINS_API_TOKEN }}"
```