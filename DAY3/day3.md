# day3 

## ROS Gazobo 虚拟仿真平台
* 使用rqt，rviz工具实时检测小车的位置，速度等信息



## 即时定位和建图 SLAM
* ROS路径规划功能包 movebase 
* global planner 全局路径规划：根据目标点的位置进行全局路径的规划
* local planner 本机路径规划：随时根据附近障碍物进行路径规划



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





