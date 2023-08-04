# PV_and_PVC_with_NFS_server
![image](https://github.com/Abhay956/PV_and_PVC_with_NFS_server/assets/132220412/88b8428a-a58f-44d4-858d-f7dcd2108226)

First To create a NFS-SERVER, run the nfs-setup.sh file on your node.


$ sh nfs-setup

Use these step in the master node.


$ apt install nfs-common -y

$ git clone https://github.com/Abhay956/PV_and_PVC_with_NFS_server.git

$ cd PV_and_PVC_with_NFS_server

Set the NFS server IP address in the pv.yml and pv2.yml files, then run the command


$ kubectl apply -f .
