# aws-fargate-test

Should have been easy to setup github actions to Aws Fargate but it was surprisingly more difficult than I expected. Maybe I didn't find the right resources but here's what I did to make it work.


Following this *incomplete* guide: https://aws.amazon.com/blogs/opensource/github-actions-aws-fargate/. Here are the modifications I made to make it work:

	• The IAM permissions are a royal pain. Need to make sure you provide ECR access for the user…
	• Also need to specify the executionRoleArn for the task-definition. Even though it wasn't quite specified clearly. Specifically, `"executionRoleArn": "ecsTaskExecutionRole"`
	• Credit to https://stackoverflow.com/questions/63673643/failed-to-register-task-definition-in-ecs-with-github-actions.
	• Copy the Dockerfile that he never provided…
Accept that seeing the new task revision as being updated on the cluster service means a successful deployment…