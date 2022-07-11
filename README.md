# seleniumTestsOnKubernetes
How to run selenium tests in kubernetes ?

PreRequisites:
Start Docker desktop
Start minikube (cmd: minikube start)
launch Kubernetes dashboard (cmd: minikube dashboard)
Deploy selenium hub in kubernetes pod 
Goto https://github.com/kubernetes/examples/tree/master/staging/selenium 
Download selenium-hub-deployment.yaml
Download kubernetes service selenium-hub-svc.yaml
Download kubernetes selenium-node-chrome-deployment.yaml
To deploy
kubectl create -f selenium-hub-deployment.yaml
Go to the dashboard where you see status hub deployment.(green status)
Deploy selenium service
kubectl create -f selenium-hub-svc.yaml
Deploy selenium-node-chrome.
kubectl create -f selenium-node-chrome-deployment.yaml

As of now, a total of 2 pods are running.
Now Run selenium grid console
minikube service selenium-hub --url
Gives us selenium grid running url with port number

Write a script such that
Create webdriver object with chromeoptions and remotewebdriver passing above url.
Run the script.
