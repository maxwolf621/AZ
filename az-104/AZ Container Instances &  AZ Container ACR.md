{%hackmd @Edixon/dracula %}
# AZ Container Instances &  AZ Container ACR

> AZ container Instance is designed for isolate container  

![image](https://hackmd.io/_uploads/Bk7QF9YUp.png)

![image](https://hackmd.io/_uploads/B1T3j9KLa.png)

![image](https://hackmd.io/_uploads/rJuAjcYLa.png)

## AZ Container Instances

### Environment Variables/ Env Vars

It is a key value pair to configure details of containers, and can be set via the AZ Portal, CLI or Powershell  

![image](https://hackmd.io/_uploads/r1sHn9Y8a.png)

### Persistent Storage

> Containers in AZ are stateless by default, all state is loss any stops or crashes 

To Persist state an external volume must be mounted.
1. AZ file, file share
2. secret volume
3. empty directory
4. cloud git repo

### Troubleshooting 

Some commands options to handle troubleshooting
1. `az container log`
2. `az container attach`
3. `az container exec`
4. `az monitor metrics list`


```bash 
# pull logs
az container logs \
    --resource-group <group_name> \
    --name <container_name>

# get diagnostic information
az container attach \
    --resource-group <group_name> \
    --name <container_name>

# start an interactive container run
az container exec \
    --resource-group <group_name> \
    --name <container_name> \
    --exec-command /bin/sh

# get specific metric talbe
az monitor metrics list \
    --resource <container_id> \
    --metric <metric_name> \
    --output table
```

### Instance Creation In MS AZ

Create Container Instance Resource : 
Container Instances | [SETUP] Basics, Networks, Advanced, Tags, Review+Create 

Check if containers
Container Instances#resource-name | Settings | Containers   
![image](https://hackmd.io/_uploads/rJKQ-jtUp.png)  

### cheatsheet

![image](https://hackmd.io/_uploads/HkEdZotI6.png)  
![image](https://hackmd.io/_uploads/HyMtbitL6.png)

## AZ Container Registry, ACR

ACR is a managed private Docker Registry Service and it stores and manages private docker container IMAGES and related artifacts.  


![image](https://hackmd.io/_uploads/Bk0DMjYIT.png)


 ### ARC tasks
 
 