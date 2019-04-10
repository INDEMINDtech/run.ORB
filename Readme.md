
不久之前，我们更新了INDEMIND双目惯性模组在ROS平台下实时运行ORB-SLAM的教程与Demo，但很多小伙伴根据教程修改后仍运行出错，这次我们把修改好的代码及文件上传至GitHub，各位同学可直接下载编译执行

### 一：环境介绍



系统：Ubuntu 16.04

ORB依赖库：Pangolin、OpenCV、Eigen3、DBoW2、g2o、ROS



### 二：下载SDK、ORB-SLAM、OpenCV 3.4.3



下载地址：



SDK：http://indemind.cn/sdk.html



ORB-SLAM：https://github.com/INDEMINDtech/run.ORB



OpenCV3.4.3：https://opencv.org/releases.html





**注意：OpenCV 3.4.3必须安装！！用户可前往我们提供的地址下载，安装教程可自行百度。**



OpenCV大致安装教程如下：



将下载的Opencv 3.4.3压缩包解压缩，然后进入到OpenCV目录



执行
```javascript
mkdir build
cd build
cmake ..
make -j(视PC线程而定,一般用2-6)
sudo make install
```


### 三：安装SDK依赖环境



安装 cmake
```javascript
sudo apt-get install cmake
```
安装 google-glog + gflags
```javascript
sudo apt-get install libgoogle-glog-dev
```
安装 BLAS & LAPACK
```javascript
sudo apt-get install libatlas-base-dev
```
安装 SuiteSparse and CXSparse
```javascript
sudo apt-get install libsuitesparse-dev
```


### 四：编译执行



将下载的ORB_SLAM2放入到……SDK/demo_ros/src目录下

 

将下载的CMakeLists.txt替换到……SDK/demo_ros/src目录下



进入……SDK/Demo_ros/src/ORB_SLAM2/Vocabulary目录下，执行


```javascript
tar -xf ORBvoc.txt.tar.gz
```

进入……SDK/demo_ros/目录，打开终端执行
```javascript
catkin_make
```

打开一个新终端，执行
```javascript
roscore
```
进入……SDK/lib/1604（或1804）下，打开终端

 

执行

```javascript
sudo -s
./run.sh
```
进入……sdk/demo_ros/目录下，打开终端，执行
```javascript
./stereo_euroc
```

**即可得到实时ORB**
