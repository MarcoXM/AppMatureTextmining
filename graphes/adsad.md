# Hadoop Wordcount Example (Windows)

## 1. Start Hadoop in cmd (Command Prompt)

Because we cannot use graphical interface AND mouse in **Command Prompt**. It is neccessary for you to be aware of in which **directory** we are operating now

![prompt](https://github.com/MarcoXM/AppMatureTextmining/blob/master/graphes/q1command.png)

After we finish Command Prompt.

We can use windows file explorer to get the address of **Hadoop'sbin folder** and *copy it*

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
