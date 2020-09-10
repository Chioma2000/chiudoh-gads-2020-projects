# LAB: Creating Virtual Machines

# Objectives: 

In this lab, you will learn how to perform the following tasks:

-Create several standard VMs

-Create advanced VMs

## Steps:

**Task 1: Create a utility virtual machine
**

#Set the VM zone to US central 1c 

gcloud config set compute/zone us-central1-c

#Configure the virtual machine

gcloud compute instances create my-instance-1 --machine-type=n1-standard-1 --subnet=default --no-address --maintenance-policy=MIGRATE --image=debian-10-buster-v20200902 --image-project=debian-cloud --boot-disk-size=10GB --boot-disk-type=pd-standard --boot-disk-device-name=my-instance-1 --no-shielded-secure-boot --no-shielded-vtpm --no-shielded-integrity-monitoring --reservation-affinity=any

**Task 2: Create a Windows virtual machine
**

#Configure the virtual machine with the defined specs

gcloud compute instances create my-windows-vm-01 --zone=europe-west2-a --machine-type=n1-standard-2 --subnet=default --network-tier=PREMIUM --maintenance-policy=MIGRATE --tags=http-server,https-server --image=windows-server-2016-dc-core-v20200813 --image-project=windows-cloud --boot-disk-size=100GB --boot-disk-type=pd-standard --boot-disk-device-name=my-windows-vm-01 --no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --reservation-affinity=any
 
gcloud compute firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server
 
gcloud compute firewall-rules create default-allow-https --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:443 --source-ranges=0.0.0.0/0 --target-tags=https-server
 
**Task 3 Create a Custom VM**

#Configure the virtual machine with the defined specs

gcloud compute instances create instancevm-3 --zone=us-west1-b --machine-type=custom-6-32768 --subnet=default --network-tier=PREMIUM --maintenance-policy=MIGRATE --image=debian-10-buster-v20200902 --image-project=debian-cloud --boot-disk-size=10GB --boot-disk-type=pd-standard --boot-disk-device-name=instancevm-3 --no-shielded-secure-boot --no-shielded-vtpm --no-shielded-integrity-monitoring --reservation-affinity=any
