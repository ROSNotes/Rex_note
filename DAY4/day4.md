#DAY4

##open cv 
* 图片
* eg：

import cv2 

img = cv2.imread('/home/intel/Desktop/image.jpg')

cv2.imshow("Display",img)

cv2.waitKey(0)

cv2.imwrite("ddads.jpg",img)

cv2.destoryAllWindows()

* 视频
* eg（旋转90度）：
import numpy as np
import cv2

cap = cv2.VideoCapture(2)

while(True):    
    ret, frame = cap.read()   
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    img90=np.rot90(gray)
    cv2.imshow('frame',frame)
    cv2.imshow('frame2',gray)
    cv2.imshow('90',img90)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

* 图形
* eg: 
绘制直线
• cv2.line(img,(0,0),(511,511),(255,0,0),5)

绘制矩形
• cv2.rectangle(img,(384,0),(510,128),(0,255,0),3)

绘制圆
• cv2.circle(img,(447,63), 63, (0,0,255), -1)

绘制椭圆
• cv2.ellipse(img,(256,256),(100,50),0,0,180,255,-1)

绘制文字
• font = cv2.FONT_HERSHEY_SIMPLEX
• cv2.putText(img,'OpenCV',(10,500), font, 4,(255,255,255),2,cv2.LINE_AA)


* 算法

##建立发布者
```
import rospy
from std_msgs.msg import String
 
def talker()
        pub = rospy.Publisher('chatter', String, queue_size=10)
        rospy.init_node('talker', anonymous=True)
        rate = rospy.Rate(10) # 10hz
        while not rospy.is_shutdown():
           hello_str = "hello world %s" % rospy.get_time()
           rospy.loginfo(hello_str)
           pub.publish(hello_str)
           rate.sleep()
   
   if __name__ == '__main__':
       try:
           talker()
       except rospy.ROSInterruptException:
           pass
```
* eg（让小车运动）：
import rospy 
from geometry_msgs.msg import Twist  

pub = rospy.Publisher('/cmd_vel',Twist,queue_size=10)
rospy.init_node('hahahah')
xuegai_rate = rospy.Rate(5)

while not rospy.is_shutdown():
  xue_cmd = Twist()
  xue_cmd.linear.x = 0
  xue_cmd.angular.z = 1

  pub.publish(xue_cmd)

  xuegai_rate.sleep()




##建立订阅者

  ```
    import rospy
    from std_msgs.msg import String
    
    def callback(data):
        rospy.loginfo(rospy.get_caller_id() + "I heard %s", data.data)
        
    def listener():
    

       rospy.init_node('listener', anonymous=True)
   
       rospy.Subscriber("chatter", String, callback)
   
  
       rospy.spin()
   
   if __name__ == '__main__':
       listener()
  ```
* eg:

import rospy
from std_msgs.msg import String
from geometry_msgs.msg import Twist

def callback(xue):
   if (xue.linear.x>0):
      rospy.loginfo("xiaowuguiqianjin")
   if (xue.linear.x<0):
      rospy.loginfo("xiaowuguihoutui")
   if (xue.angular.z>0):
      rospy.loginfo("xiaowuguizuozhuan")
   if (xue.angular.z<0):
      rospy.loginfo("xiaowuguiyouzhuan")
     
def listener():
   
   rospy.init_node('listener', anonymous=True)   
   rospy.Subscriber("cmd_vel", Twist, callback)
   rospy.spin()
   
if __name__ == '__main__':
       listener()


