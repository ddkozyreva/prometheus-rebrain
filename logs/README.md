# Node Exporter Dashboard

```
user@node1:~$ sudo systemctl start node_exporter.service 
user@node1:~$ sudo systemctl status node_exporter.service 
● node_exporter.service - Node Exporter
     Loaded: loaded (/etc/systemd/system/node_exporter.service; disabled; vendor preset: enabled)
     Active: active (running) since Wed 2024-07-17 20:58:21 UTC; 8s ago
   Main PID: 20350 (node_exporter)
      Tasks: 3 (limit: 2344)
     Memory: 5.4M
     CGroup: /system.slice/node_exporter.service
             └─20350 /home/user/node_exporter/node_exporter
user@node1:~$ 
```

```
#/var/log/syslog

Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.246Z caller=node_exporter.go:193 level=info msg="Starting node_exporter" version="(version=1.8.2, branch=HEAD, revision=f1e0e8360aa60b6cb5e5cc1560bed348fc2c1895)"
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.247Z caller=node_exporter.go:194 level=info msg="Build context" build_context="(go=go1.22.5, platform=linux/amd64, user=root@03d440803209, date=20240714-11:53:45, tags=unknown)"
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.248Z caller=node_exporter.go:196 level=warn msg="Node Exporter is running as root user. This exporter is designed to run as unprivileged user, root is not required."
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.248Z caller=diskstats_common.go:111 level=info collector=diskstats msg="Parsed flag --collector.diskstats.device-exclude" flag=^(z?ram|loop|fd|(h|s|v|xv)d[a-z]|nvme\d+n\d+p)\d+$
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.250Z caller=filesystem_common.go:111 level=info collector=filesystem msg="Parsed flag --collector.filesystem.mount-points-exclude" flag=^/(dev|proc|run/credentials/.+|sys|var/lib/docker/.+|var/lib/containers/storage/.+)($|/)
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.250Z caller=filesystem_common.go:113 level=info collector=filesystem msg="Parsed flag --collector.filesystem.fs-types-exclude" flag=^(autofs|binfmt_misc|bpf|cgroup2?|configfs|debugfs|devpts|devtmpfs|fusectl|hugetlbfs|iso9660|mqueue|nsfs|overlay|proc|procfs|pstore|rpc_pipefs|securityfs|selinuxfs|squashfs|sysfs|tracefs)$
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.251Z caller=node_exporter.go:111 level=info msg="Enabled collectors"
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.253Z caller=node_exporter.go:118 level=info collector=arp
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.253Z caller=node_exporter.go:118 level=info collector=bcache
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.253Z caller=node_exporter.go:118 level=info collector=bonding
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.254Z caller=node_exporter.go:118 level=info collector=btrfs
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.254Z caller=node_exporter.go:118 level=info collector=conntrack
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.254Z caller=node_exporter.go:118 level=info collector=cpu
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.254Z caller=node_exporter.go:118 level=info collector=cpufreq
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.254Z caller=node_exporter.go:118 level=info collector=diskstats
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.254Z caller=node_exporter.go:118 level=info collector=dmi
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.255Z caller=node_exporter.go:118 level=info collector=edac
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.255Z caller=node_exporter.go:118 level=info collector=entropy
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.255Z caller=node_exporter.go:118 level=info collector=fibrechannel
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.255Z caller=node_exporter.go:118 level=info collector=filefd
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.255Z caller=node_exporter.go:118 level=info collector=filesystem
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=hwmon
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=infiniband
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=ipvs
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=loadavg
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=mdadm
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=meminfo
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=netclass
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=netdev
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=netstat
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=nfs
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=nfsd
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=nvme
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=os
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=powersupplyclass
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=pressure
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=rapl
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=schedstat
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=selinux
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=sockstat
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=softnet
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=stat
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=tapestats
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=textfile
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=thermal_zone
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=time
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=timex
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=udp_queues
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=uname
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=vmstat
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=watchdog
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=xfs
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.256Z caller=node_exporter.go:118 level=info collector=zfs
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.260Z caller=tls_config.go:313 level=info msg="Listening on" address=[::]:9100
Jul 17 20:58:21 node1 node_exporter[20350]: ts=2024-07-17T20:58:21.260Z caller=tls_config.go:316 level=info msg="TLS is disabled." http2=false address=[::]:9100
Jul 17 20:58:25 node1 systemd[1]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.OKFZAn.mount: Succeeded.
Jul 17 20:58:25 node1 systemd[2407]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.OKFZAn.mount: Succeeded.
Jul 17 20:58:55 node1 systemd[2407]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.de6d3M.mount: Succeeded.
Jul 17 20:58:55 node1 systemd[1]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.de6d3M.mount: Succeeded.
Jul 17 20:59:25 node1 systemd[2407]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.gxSFG0.mount: Succeeded.
Jul 17 20:59:25 node1 systemd[1]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.gxSFG0.mount: Succeeded.
user@node1:~$ 
```


# Mysqld Exporter Dashboard

```
user@node1:~$ sudo systemctl start mysqld_exporter.service 
user@node1:~$ sudo systemctl status mysqld_exporter.service 
● mysqld_exporter.service - Mysqld Exporter
     Loaded: loaded (/etc/systemd/system/mysqld_exporter.service; disabled; vendor preset: enabled)
     Active: active (running) since Wed 2024-07-17 21:02:12 UTC; 5s ago
   Main PID: 20744 (mysqld_exporter)
      Tasks: 3 (limit: 2344)
     Memory: 1.7M
     CGroup: /system.slice/mysqld_exporter.service
             └─20744 /home/user/mysqld_exporter/mysqld_exporter --config.my-cnf=/home/user/mysqld_exporter/config.my-cnf
```
```
#/var/log/syslog
Jul 17 21:02:12 node1 systemd[1]: Started Mysqld Exporter.
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.555Z caller=mysqld_exporter.go:220 level=info msg="Starting mysqld_exporter" version="(version=0.15.1, branch=HEAD, revision=cc349684494b5038ec5a52233bdca9eb9291e6f2)"
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.556Z caller=mysqld_exporter.go:221 level=info msg="Build context" build_context="(go=go1.21.5, platform=linux/amd64, user=root@d89c15b9f5ad, date=20231212-07:55:09, tags=unknown)"
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.560Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=global_status
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.561Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=global_variables
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.561Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=slave_status
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.561Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=info_schema.innodb_cmp
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.562Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=info_schema.innodb_cmpmem
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.562Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=info_schema.query_response_time
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.565Z caller=tls_config.go:274 level=info msg="Listening on" address=[::]:9104
Jul 17 21:02:12 node1 mysqld_exporter[20744]: ts=2024-07-17T21:02:12.565Z caller=tls_config.go:277 level=info msg="TLS is disabled." http2=false address=[::]:9104
Jul 17 21:02:26 node1 systemd[2407]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.sVBfNj.mount: Succeeded.
Jul 17 21:02:26 node1 systemd[1]: run-docker-runtime\x2drunc-moby-9ac7fd3abb4726eb193a2006da5ce753a9a7dc63c669c510e6cac41540ef82b4-runc.sVBfNj.mount: Succeeded.
```


# Cadvisor Dashboard

```
user@node1:~$ sudo docker run \
>   --volume=/:/rootfs:ro \
>   --volume=/var/run:/var/run:ro \
>   --volume=/sys:/sys:ro \
>   --volume=/var/lib/docker/:/var/lib/docker:ro \
>   --volume=/dev/disk/:/dev/disk:ro \
>   --publish=8080:8080 \
>   --detach=true \
>   --name=cadvisor \
>   --privileged \
>   --device=/dev/kmsg \
>   gcr.io/cadvisor/cadvisor:v0.49.1
Unable to find image 'gcr.io/cadvisor/cadvisor:v0.49.1' locally
v0.49.1: Pulling from cadvisor/cadvisor
619be1103602: Pull complete 
3b8469b194b8: Pull complete 
6361eeb1639c: Pull complete 
4f4fb700ef54: Pull complete 
902eccca70f3: Pull complete 
Digest: sha256:3cde6faf0791ebf7b41d6f8ae7145466fed712ea6f252c935294d2608b1af388
Status: Downloaded newer image for gcr.io/cadvisor/cadvisor:v0.49.1
1d1b3ba6dc4838557db4eb1eeee6a57e3083162d13eb2f26920b94cb9dc2aac7
user@node1:~$ sudo docker ps
CONTAINER ID   IMAGE                              COMMAND                  CREATED         STATUS                            PORTS                                       NAMES
1d1b3ba6dc48   gcr.io/cadvisor/cadvisor:v0.49.1   "/usr/bin/cadvisor -…"   9 seconds ago   Up 8 seconds (health: starting)   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp   cadvisor
98de7d43f749   wordpress:latest                   "docker-entrypoint.s…"   2 hours ago     Up 2 hours                        0.0.0.0:8000->80/tcp, :::8000->80/tcp       wordpress_data-wordpress-1
cd63214bee9c   mysql:5.7                          "docker-entrypoint.s…"   2 hours ago     Up 2 hours                        3306/tcp, 33060/tcp                         wordpress_data-db-1
```