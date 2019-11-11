# gwendolen-rosbridge
Jason environment that allows agents to publish/subscribe to ROS topics using rosbridge.

We are using the [java_rosbridge](https://github.com/h2r/java_rosbridge) library to connect to rosbridge using Java code.

To test:
1. Install [Jason](http://jason.sourceforge.net/) using the Eclipse plug-in, and make sure it is working
2. Install ROS, any version, and make sure it is working
3. Install [Rosbridge](http://wiki.ros.org/rosbridge_suite/Tutorials/RunningRosbridge) for the ROS version that you installed (and make sure it is working!)
4. Import from git
5. Start ROS with rosbridge in a terminal using `roslaunch rosbridge_server rosbridge_websocket.launch`
6. Open another terminal and use the command `rostopic echo /java_to_ros` (this is where messages from Jason will appear)
7. In Eclipse, right-click `hello_ros.mas2j`, select Run Jason Application
   * You should see the messages from Jason agents in the terminal from step 6
8. To test the subscriber, open another terminal and type `rostopic pub ros_to_java std_msgs/String "hello from ros"`
   * You should see "hello from ros" in the Jason MAS console
