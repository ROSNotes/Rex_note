#DAY2

##Github  
*git clone 远程克隆仓储
*git status 仓储当前状态
*git push 推送

*上传笔记
1,git add. 添加更改
2,git commit -m "备注"
3,git push 推送
4,输入github用户名和密码


##ROSE turtleism 

*roscore 
*rosrun turtlesim_node   小乌龟
*rosrun turtlesim turtle_teleop_key 键盘操作

##ROS结构

publisher -- topic -- subscriber 
rqt_graph 节点关系图

*ROS master 节点管理器
*rosnode （ROS node)节点
*rostopic (ROS Topic)话题
list  列出话题
find 通过type找到话题
info 列出信息（订阅者 发布者）
pub 给话题发布消息
*rosmsg (ROS message)消息


##建立工作空间 创造功能包
1,建立文件夹 catkin_ws/src
2,src文件夹下初始化工作空间  catkin_init_workspace
3,编译 工作空间的根目录下 catkin_make 
4,创建功能包 catkin_create_pkg turtlesim_bringup name rospy
5,在功能包里创建launch文件并输入 
<launch>
  <node name="talker" pkg="rospy_tutorials" type="talker" />
 <node name="talker" pkg="rospy_tutorials" type="talker" />
</launch>
6,启动launch文件 roslaunch name.launch
