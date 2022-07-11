# seleniumTestsOnKubernetes
How to run selenium tests in kubernetes ?

## Steps to setup:
Start Docker desktop  <br />
Start minikube (cmd: minikube start) <br />
launch Kubernetes dashboard (cmd: minikube dashboard) <br />
Deploy selenium hub in kubernetes pod  <br />
Goto <br /> https://github.com/kubernetes/examples/tree/master/staging/selenium  <br />
Download selenium-hub-deployment.yaml <br />
Download kubernetes service selenium-hub-svc.yaml <br />
Download kubernetes selenium-node-chrome-deployment.yaml <br />
### To deploy <br />
kubectl create -f selenium-hub-deployment.yaml <br />
Go to the dashboard where you see status hub deployment.(green status) <br />
Deploy selenium service <br />
kubectl create -f selenium-hub-svc.yaml <br />
Deploy selenium-node-chrome. <br />
kubectl create -f selenium-node-chrome-deployment.yaml <br />

As of now, a total of 2 pods are running. <br />
Now Run selenium grid console <br />
minikube service selenium-hub --url <br />
Gives us selenium grid running url with port number <br />

### Running script <br />
Write a script such that <br />
Create webdriver object with chromeoptions and remotewebdriver passing above url. <br />
Run the script. <br />
