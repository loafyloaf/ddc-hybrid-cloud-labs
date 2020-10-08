Use the very top drop down in the navigation menu on the left to switch to *Developer** view

![developer view](../.gitbook/generic/developerview.png)

Click **+Add** and select the Database tile

![add database](../.gitbook/generic/adddatabase.png)

Choose the **Database Database** tile and then **Create**

![database](../.gitbook/generic/databasedatabase.png)

You can edit some of the specifics of the database here.  For example, change the name to `creditdb` and click **Create**

![create database](../.gitbook/generic/createdatabase.png)

Switch to the Topology tab, and watch your database creation complete!

![topology](../.gitbook/generic/topology.png)
Use the very top drop down in the navigation menu on the left to switch to *Developer** view

![developer view](../.gitbook/generic/developerview.png)

Click **+Add** and select the Database tile

![add database](../.gitbook/generic/adddatabase.png)

Choose the **Database Database** tile and then **Create**

![database](../.gitbook/generic/databasedatabase.png)

You can edit some of the specifics of the database here.  For example, change the name to `creditdb` and click **Create**

![create database](../.gitbook/generic/createdatabase.png)

Switch to the Topology tab, and watch your database creation complete!

![topology](../.gitbook/generic/topology.png)
Use the IBM Cloud console to launch the OpenShift web console

![web console](../.gitbook/generic/webconsole.png)

First create an 'Example Bank' namespace

![create project](../.gitbook/generic/createproject.png)

From the navigation menu on the left select **Operators** --> **OperatorHub**

![operatorhub](../.gitbook/generic/operatorhub.png)

Type 'Postgres' into the search bar, and select the **PostgreSQL Operator by Dev4Ddevs.com** tile.

![postgres operator](../.gitbook/generic/postgresoperator.png)

Click **Continue** to show the community operator and then **Install**

![install operator](../.gitbook/generic/installoperator.png)

Be sure you are installing the Operator in the `Example Bank` namespace, and click **Subscribe**

![subscribe](../.gitbook/generic/subscribe.png)

Status will show "Succeeded: Up to date" when complete

![succeeded](../.gitbook/generic/subscribe.png)
Now we will need some CLI access.  First, go to https://labs.cognitiveclass.ai and start a **Theia - Cloud IDE (With OpenShift)** session

![cognitiveclass](../.gitbook/generic/cognitiveclass.png)

back on your OpenShift web console, click you email address in the upper right corner and choose **Copy Login Command**

![copy login command](logincommand.png)

From the resulting screen, grab your login credentials, and copy them into your ClognitiveClass terminal

![clusterlogin](../.gitbook/generic/clusterlogin.png)

switch to the example bank project

```
git clone https://github.com/IBM/example-bank
```

Create a secret so the script that loads the schema can access the database

```
kubectl create secret generic bank-db-secret --from-literal=DB_SERVERNAME=creditdb --from-literal=DB_PORTNUMBER=5432 --from-literal=DB_DATABASENAME=example --from-literal=DB_USER=postgres --from-literal=DB_PASSWORD=postgres
```

Run the script to create the schema

```
oc apply -f data_model/job.yaml
```

![schema](https://raw.githubusercontent.com/IBM/example-bank/main/images/schema-1.png)

Use the IBM Cloud console to launch the OpenShift web console

![web console](../.gitbook/generic/webconsole.png)

First create an 'Example Bank' namespace

![create project](../.gitbook/generic/createproject.png)

From the navigation menu on the left select **Operators** --> **OperatorHub**

![operatorhub](../.gitbook/generic/operatorhub.png)

Type 'Postgres' into the search bar, and select the **PostgreSQL Operator by Dev4Ddevs.com** tile.

![postgres operator](../.gitbook/generic/postgresoperator.png)

Click **Continue** to show the community operator and then **Install**

![install operator](../.gitbook/generic/installoperator.png)

Be sure you are installing the Operator in the `Example Bank` namespace, and click **Subscribe**

![subscribe](../.gitbook/generic/subscribe.png)

Status will show "Succeeded: Up to date" when complete

![succeeded](../.gitbook/generic/subscribe.png)
Now we will need some CLI access.  First, go to https://labs.cognitiveclass.ai and start a **Theia - Cloud IDE (With OpenShift)** session

![cognitiveclass](../.gitbook/generic/cognitiveclass.png)

back on your OpenShift web console, click you email address in the upper right corner and choose **Copy Login Command**

![copy login command](logincommand.png)

From the resulting screen, grab your login credentials, and copy them into your ClognitiveClass terminal

![clusterlogin](../.gitbook/generic/clusterlogin.png)

switch to the example bank project

```
git clone https://github.com/IBM/example-bank
```

Create a secret so the script that loads the schema can access the database

```
kubectl create secret generic bank-db-secret --from-literal=DB_SERVERNAME=creditdb --from-literal=DB_PORTNUMBER=5432 --from-literal=DB_DATABASENAME=example --from-literal=DB_USER=postgres --from-literal=DB_PASSWORD=postgres
```

Run the script to create the schema

```
oc apply -f data_model/job.yaml
```

![schema](https://raw.githubusercontent.com/IBM/example-bank/main/images/schema-1.png)

