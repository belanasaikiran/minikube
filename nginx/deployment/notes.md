#update Deployment


1. update using `set` command:
``k set image deploy nginx-deploy nginx-container=nginx=1.9.1`` 

2. update using `edit` command: manually edit and once exited it will auto update
``k edit deploy nginx-deploy``

Status of Update:  using `rollout`: shows the rollout status
``k rollout status deployment/nginx-deployment``


check deployment:
``k get deploy``



#Rollback Deployment

1. Go back to previous stable version using `rollout undo` command:
``k rollout undo deployment/nginx-deployment``

2. check the rollout status:
``k rollout status deployment/nginx-deployment``



#Scaling Up & Down 

if users are increasing, then do the following

1. Scale up:
k scale deploy nginx-deploy --replicas=5

2. scale down:
k scale deploy nginx-deploy --replicas=1

To Verify:
k get deploy

k get po -l app-nginx-app


#delete:

k delete -f nginx-deploy.yaml
