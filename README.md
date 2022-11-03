# jason-rosbridge
Jason environment that allows agents to publish/subscribe to ROS topics using rosbridge.

Works for all ROS 1 and ROS 2 distros that support the rosbridge library.

We are using the [java_rosbridge](https://github.com/h2r/java_rosbridge) library to connect to rosbridge using Java code.

To test:
1. Install [Jason](http://jason.sourceforge.net/), and make sure it is working
2. Install ROS, any version, and make sure it is working
3. Install [Rosbridge](http://wiki.ros.org/rosbridge_suite/Tutorials/RunningRosbridge) for the ROS version that you installed (and make sure it is working!)
4. Load this project in whatever way you are using to run Jason projects (Eclipse, jEdit, gradle, etc.)
5. Start ROS with rosbridge in a terminal using:   
   * For ROS 1: `roslaunch rosbridge_server rosbridge_websocket.launch`
   * For ROS 2: `ros2 launch rosbridge_server rosbridge_websocket_launch.xml`
6. Open another terminal (remember to source your ROS distro) and use the command:
   * For ROS 1: `rostopic echo /java_to_ros`
   * For ROS 2: `ros2 topic echo /java_to_ros`
7. Run this Jason project (we suggest using Gradle: `./gradlew run`)
   * You should see the messages from Jason agents in the terminal from step 6
8. To test the subscriber, open another terminal and type:
   * For ROS 1: `rostopic pub ros_to_java std_msgs/String "hello from ros"`
   * For ROS 2: `ros2 topic pub /ros_to_java std_msgs/String "data: hello from ros"`
   * You should see "hello from ros" in the Jason MAS console
