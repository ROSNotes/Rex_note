# DAY3 

## ROS Gazobo 虚拟仿真平台
* 使用rqt，rviz工具实时检测tutlrbot的位置，速度等信息
* 启动turtlebot gazebo gmapping 建图功能包
* 启动turtlebot gazebo Amcl导航功能包



## 即时定位和建图 SLAM
* ROS路径规划功能包 movebase 
* global planner 全局路径规划：根据目标点的位置进行全局路径的规划
* local planner 本机路径规划：随时根据附近障碍物进行路径规划

#### AMCL定位算法功能包
* Subscribed Topics(订阅的话题)
scan (sensor_msgs/LaserScan) (激光雷达)
tf (tf/tfMessage)(TF坐标变换)
initialpose (geometry_msgs/PoseWithCovarianceStamped) (里程计)
map (nav_msgs/OccupancyGrid)(栅格地图)
* Published Topics(发布的话题)
amcl_pose (geometry_msgs/PoseWithCovarianceStamped)(里程)
particlecloud (geometry_msgs/PoseArray)位姿()
tf (tf/tfMessage)(里程计到地图的坐标变换) 

### 建立地图
* 启动 roslaunch mx_bringup rbc_camera_start.launch
或者roslaunch mx_bringup rbc_lidar_start.launch
* 启动 roslaunch mx_nav gmapping_demo.launch rvizview:=1
保存地图
* 启动 roslaunch mx_nav map_save.lanch

### 导航
* 启动 roslaunch mx_bringup rbc_camera_start.launch
或者roslaunch mx_bringup rbc_lidar_start.launch
* 启动 roslaunch mx_nav amcl_demo.launch rviz_view:=1
* 使用 2d nav goal 标记目标点
* 使用rqt里的dynamic reconfigure里的movebase实时调整参考数值





