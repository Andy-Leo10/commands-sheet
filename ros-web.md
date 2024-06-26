# ROS Web

- [ROS Web](#ros-web)
  - [Resources available:](#resources-available)
  - [For starting the web server:](#for-starting-the-web-server)
  - [For starting the camera:](#for-starting-the-camera)
  - [For accessing urls if were set:](#for-accessing-urls-if-were-set)

## Resources available:
https://robotwebtools.github.io/

## For starting the web server:
```
cd ~/PATH_TO_WEB
http-server --port 7000
python -m simpleHTTPServer 7000
```

## For starting the camera:
```
rosrun web_video_server web_video_server -port:=11315
```

--------------------------------------------

> **CHECK**:
> ```
> roslaunch course_web_dev_ros course.launch
> ```

## For accessing urls if were set:
```
webpage_address: http://localhost:8080
web_video_address: http://localhost:8080/stream?topic=/camera/image_raw
rosbridge_address: ws://localhost:9090
```

