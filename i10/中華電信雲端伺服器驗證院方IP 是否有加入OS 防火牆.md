---

Created at: 2023-12-26
Last updated at: 2024-05-27


---

# 中華電信雲端伺服器驗證院方IP 是否有加入OS 防火牆


注意只有中華電信的雲端需要執行方火牆IP 加入,公司端的不用執行
IP :210.65.11.86
root/smx##801001
排程執行
\*/5 8-18 \* \* \* root /bin/sh /home/IPForwardRedirect/runIPForwardRedirect.sh >> /home/IPForwardRedirect/Logs.log
![[i10/_resources/中華電信雲端伺服器驗證院方IP_是否有加入OS_防火牆.resources/image.1.png]]
先執行以下確認有沒有
```
grep "院方IP" /home/IPForwardRedirect/Logs.log
```

![[i10/_resources/中華電信雲端伺服器驗證院方IP_是否有加入OS_防火牆.resources/image.png]]
若沒有就執行以下
```
/bin/sh /home/IPForwardRedirect/runIPForwardRedirect.sh >> /home/IPForwardRedirect/Logs.log
```
在驗證看看
grep "211.21.30.90" /home/IPForwardRedirect/Logs.log
![[i10/_resources/中華電信雲端伺服器驗證院方IP_是否有加入OS_防火牆.resources/image.2.png]]
範例:
IP:60.248.250.138,202.39.133.71,211.22.15.99 查詢是否有新增到 hinet clould
login as: root
root@210.65.11.86's password:
Last login: Mon Mar 11 17:45:51 2024 from 59-120-248-193.hinet-ip.hinet.net

\[root@chttl-986df84a533abc82 ~\]#
\[root@chttl-986df84a533abc82 ~\]#
\[root@chttl-986df84a533abc82 ~\]#
\[root@chttl-986df84a533abc82 ~\]# crontab -l
0 1 \* \* \* /usr/sbin/ntpdate tock.stdtime.gov.tw && /sbin/hwclock -w >/dev/null 2>&1

\*/5 8-18 \* \* \* root /bin/sh /home/IPForwardRedirect/runIPForwardRedirect.sh >> /home/IPForwardRedirect/Logs.log
#\*/5 8-18 \* \* \* root echo "test-"\`date +%Y%m%d%H%M\` > /home/IPForwardRedirect/Run.log

\[root@chttl-986df84a533abc82 ~\]# root /bin/sh /home/IPForwardRedirect/runIPForwardRedirect.sh >> /home/IPForwardRedirect/Logs.log
\-bash: root: command not found
\[root@chttl-986df84a533abc82 ~\]# /bin/sh /home/IPForwardRedirect/runIPForwardRedirect.sh >> /home/IPForwardRedirect/Logs.log
\[root@chttl-986df84a533abc82 ~\]# grep "60.248.250.138" /home/IPForwardRedirect/Logs.log
60.248.250.138...(新增完成)
\[root@chttl-986df84a533abc82 ~\]# grep "202.39.133.71" /home/IPForwardRedirect/Logs.log
202.39.133.71...(新增完成)
\[root@chttl-986df84a533abc82 ~\]# grep "211.22.15.99" /home/IPForwardRedirect/Logs.log
211.22.15.99...(新增完成)
\[root@chttl-986df84a533abc82 ~\]#

