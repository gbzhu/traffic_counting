
#### 工作目录 

`/home/student5/gbzhu`

1. 先上传数据文件

```shell
hdfs dfs -mkdir /user/gbzhu
```

```shell
hdfs dfs -put HTTP_20130313143750.dat /user/gbzhu/
```
2. 查询文件

```shell
hdfs dfs -ls /user/gbzhu
Found 1 items
-rw-r-----   2 student5 hadoop       2209 2022-03-13 19:33 /user/gbzhu/HTTP_20130313143750.dat
```

3. 执行作业
```shell
hadoop jar $HOME/gbzhu/trafficcount.jar com.example.trafficcount.TrafficCount
```

4. 下载输出
```shell
hdfs dfs -get /user/gbzhu/output
```

5. 打印输出
```shell
find output -name "part-*" | while read line; do
  cat $line
  done
13560439658     2034    5892
13925057413     11058   48243
15013685858     3659    3538
15920133257     3156    2936
15989002119     1938    180
13660577991     6960    690
13760778710     120     120
13922314466     3008    3720
18320173382     9531    2412
13480253104     180     180
13926251106     240     0
13726238888     2481    24681
13560436666     1116    954
13726230503     2481    24681
13926435656     132     1512
18211575961     1527    2106
13502468823     7335    110349
13602846565     1938    2910
84138413        4116    1432
13719199419     240     0
13826544101     264     0
```
