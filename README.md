
## PV_and_PVC_with_NFS_server

![image](https://github.com/Abhay956/PV_and_PVC_with_NFS_server/assets/132220412/88b8428a-a58f-44d4-858d-f7dcd2108226)

### Before you start.

For this example, you need a Kubernetes cluster and one other node for the NFS server. First, you create the NFS server by running the script nfs-setup.sh. This script will create an NFS server for you in 1 minutes.

first, Create NFS-server.

```bash
  $ sh nfs-setup.sh
```

All of these commands are then executed on the master-node.
```bash
  $ apt install nfs-common -y
```
Now, git clone ropo on the master node. Then make changes to the pv.yml and pv2.yml files in the ropo directory. In the files, enter your NFS server IP address. Once you have made the changes, use the apply command.
```bash
  $ kubectl apply -f .

```
Verify that your data is replicated on the NFS server. To do this, enter your MySQL pod and go to the directory /var/lib/mysql. Create a file in this directory.
```bash
  $ kubectl exec -it mysql-pod-name -- bash
```
Then go to this directory.
```bash
  $ cd /var/lib/mysql
```
Create some files to replicate those files.
```bash
  $ touch mydata{1..10}.txt
```
Now check that the data is replicated to your NFS server directory.
![image](https://github.com/Abhay956/PV_and_PVC_with_NFS_server/assets/132220412/a55306d4-f4a2-482a-a6af-381e9e1a7f16)


