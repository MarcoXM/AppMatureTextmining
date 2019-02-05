# Hadoop Wordcount Example (Windows)

## 1. Start Hadoop in cmd (Command Prompt)

Because we cannot use graphical interface AND mouse in **Command Prompt**. It is neccessary for you to be aware of in which **directory** we are operating now

![prompt](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/q1command.png)

After we finish Command Prompt.

We can use windows file explorer to get the address of **Hadoop'sbin folder** and *copy it*

> cd : change directory

then we could paste *the address* in **command prompt** like this below

```
cd c:\Hadoop-2.8.0\sbin
```
![where](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/command_hadoop.png)

Notice that the last few words in the comment line have changed into 

```
xxxx\xxxx\sbin>
```
So we are in the **right directory** to start running **Hadoop!!!**

Now by typing this command
```
start-all.cmd 
```
to start running Hadoop.

![chuankou](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/3%20windows%20show.png)

When those windows show up, which means we are on the right way.

After a few seconds, typing
```
jps
```
to make sure that all parts of HDFS are running.
![what](After a few seconds, use jps to make sure that all parts of HDFS are running.)

## 2. Create a new directory in HDFS
Start in *s*bin folder, but we should operate hadoop in **bin folder**.

In order to switch directory from one to the neightbor one, we could use :
```
cd ..\bin
```
**Because we could know bin and sbin are in Hadoop2.8.0 folder.**

![IN_BIN](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/in_.png)

OK~, we are in **bin** now. Then we are going to create a folder by the command below
```
hdfs dfs -mkdir -p /data/
```
Notice that the word between two / xxxxx / would be the name of the new folder in HDFS.

And another example: to create a new folder——datanew
！[new](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/NEW_2.png)

Now you could notice that there have **data folder and datanew folder** in our HDFS.

## 3. Transfer a txt file into HDFS

Yup, we are still in **bin** folder. Then we could using the instruction below:

```
hdfs dfs -put the address where you put thetxt file\shakespeare.txt /datanew/ 

**example of mine**
hdfs dfs -put D:\Downloads\shakespeare.txt /datanew/
```
to transfer the txt file into HDFS.

![result](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/result.png)
We could find that the shakespeare is in HDFS now.

## 4.Start wordcount program

![IN_HA](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/cd.png)
```
hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.8.0.jar wordcount /datanew/ /datanew/output/result
```
to require a wordcount process in Hadoop program.
```
/datanew/
```
is the folder you just created.
```
/datanew/output/result 
```
is the folder automatically created by HDFS and all results will be saved in **/result/** folder.

![JAR](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/jar.png)
Running.

When the wordcount process finished, your cmd will look like the image below:

![wan](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/running.png)

## 5.Let’s check our results and save it

Browse the file system in localhost.

![a](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/hd.png)

You will find the “part-r-00000” file.

Now we need to change the current directory into **“bin”** folder and use instruction below in command
```
hdfs dfs -cat /datanew/output/result/part-r-00000
```

![cat](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/cat.png)
to read and show the contents in “part-r-00000” file.

In windows Hadoop2.8.0 folder, creating a folder named **output** to store the HDFS result.

![adasd](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/outfo.png)


Then typing in command with instruction below in Hadoop 2.8.0 folder instead of in xbin folder:
```
hadoop fs -get /datanew/output/result/part-r-00000 D:\hadoop-2.8.0\output
```
to download the result file **“part-r-00000”** from HDFS.

![sds](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/store.png)

We open the data with **notepad** in windows. And then save it in txt or csv file as you like.



## 6. Stop Hadoop in cmd (Properly close is important)
![INBIN](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/stop.png)
Using
```
stop-all.cmd 
```
in **sbin** folder (where we start running) to stop Hadoop. (Image below is the right status of Hadoop after stopped.)
![FINAL](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/final.png)





