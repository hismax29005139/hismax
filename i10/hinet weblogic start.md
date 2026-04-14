---

Created at: 2022-05-17
Last updated at: 2023-12-25


---

# hinet weblogic start


先登入hinet cloud  (210.65.11.86\_hinetCloud)
login : root
```
su - weblogic
```

```
cd $base
```

![[unknown_filename.3.png]]![[unknown_filename.4.png]]
啟動weblogic 服務
```
nohup ./startWebLogic.sh &
```

![[unknown_filename.6.png]]
ps -defa |grep weblogic
![[unknown_filename.7.png]]![[i10/_resources/hinet_weblogic_start.resources/unknown_filename.1.png]]

```
cd
cd Oracle/
cd Middleware/
cd wlserver_10.3/
cd server/
cd bin
nohup sh ./startNodeManager.sh &
```
啟動nodeManager 
![[i10/_resources/hinet_weblogic_start.resources/unknown_filename.png]]![[unknown_filename.2.png]]
連線console 啟動站台服務 (Server\_auth)
<http://210.65.11.86:7001/console>

weblogic / max!3366224

![[unknown_filename.5.png]]
測試連線
<http://210.65.11.86:7003/Icd10_Web/> 

![[unknown_filename.8.png]]

