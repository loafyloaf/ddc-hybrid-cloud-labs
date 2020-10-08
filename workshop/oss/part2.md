# Part 2

In this part, we will deploy the images built in part 1 to our cluster.

> Update YAML deployment manifests to point at correct images:


```
1. bank-app-backend/transaction-service/deployment.yaml ==> <your_dockerhub>/lab-transaction:1.0

2. bank-app-backend/user-service/deployment.yaml ==> <your_dockerhub>/lab-user:1.0

3. bank-user-cleanup-utility/job.yaml ==> <your_dockerhub>/lab-erasure:1.0
```

* Note: The mobile simulator is already deployed.

> Now, we can deploy the services:
```
oc apply -f bank-app-backend/user-service/deployment.yaml -f bank-app-backend/transaction-service/deployment.yaml -f bank-user-cleanup-utility/job.yaml
```

> Wait until deployments are complete.

Find route to access simulator:

```
theia@theiadocker-koyfman1:/home/project/example-bank$ oc get routes | grep simulator
```
