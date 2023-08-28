<div align="center">

# Nessus docker 


This project is only for non-profit learning research. Do not use it for illegal purposes. If there is any infringement, please contact it in time to delete it.
</div>

# Usage
``` bash
docker run -itd --name=ramisec_nessus -p 8834:8834 ramisec/nessus
```  
(497MB Only!!!)

That's right, easy like that! But it need update the plugins with the following command. 🤣

# Update
``` bash
docker exec -it ramisec_nessus /bin/bash /nessus/update.sh
```  


__Alert__  
If you CAN NOT update successful, please CHECK the network connection!

# Migration

If you need to migrate from old versions to new, use the following command

```bash
# Crate dir
mkdir ~/nessus_data
# Stop container
docker stop ramisec_nessus
# copy data
docker cp ramisec_nessus:/opt/nessus/var/nessus/ ~/nessus_data
# delete old container
docker rm ramisec_nessus
# run new container
docker run -itd --name=ramisec_nessus -v ~/nessus_data/nessus/:/opt/nessus/var/nessus/ -p 8834:8834 ramisec/nessus
# update plugins
docker exec -it ramisec_nessus /bin/bash /nessus/update.sh
```

# Account & Password

account: `admin`

Execute into container using cli like below
```Bash
/opt/nessus/sbin/nessuscli chpasswd admin
```

# Update log

## v4 20230523

- Fix Timezone error

- Add scan data migration

- Change password

  **tips：npaobi/lsspva-iph/ulzzbz**

  **Alea iacta est，Destiny reveals that your lucky number is 7.**

## v3 20220722

__Big update：auto-update plugins version has release！__

usage： `docker run -itd --name=ramisec_nessus -p 8834:8834 ramisec/nessus`  
The container had no plugins, it need to update by following command:  
`docker exec -it ramisec_nessus /bin/bash /nessus/update.sh`  
and it can be update again next time by the same command ！



## v2 20220621

Update the latest version of 20220620, and use 2 versions of NESSUS/JESSUSLITE  
The former has been cracked and compiled the plug -in.  
The latter needs to wait a few minutes to compile the plug -in  
password:  
`U2FSDGVKX19WZV+Qoe8awvyjwxDPSNSIC1X4AMNA4+3RO8ml/3Hz+MS/OR3DHCWXKS0WHFVOH1Q/yntvdxnahg ==`  

__TIPS__: gitHub/elliot-bia


> ~~# Old Usage~~
> ~~`docker run -itd -p 8834:8834 ramisec/nessus`   (4.73GB)~~
> ~~ or~~  
> ~~`docker run -itd -p 8834:8834 ramisec/nessuslite` (3.55GB)~~ 
> ~~The former does not require compilation and is suitable for low-performance high-bandwidth machines~~  
> ~~The latter requires compilation and is suitable for high-performance low-bandwidth machines~~  
> ~~What? high-performance and high-bandwidth machines? Never mind, just use it! have fun!~~

In fact, there is another EASY way to solved the encryption, try and find it!😆

# Thanks note
Some English text translated by [Aholicknight](https://github.com/Aholicknight)

thanks a lot! 


