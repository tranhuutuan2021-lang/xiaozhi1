# RobotAnno SJ602-A integration

This source tree has been modified so the Xiaozhi ESP device exposes these MCP tools:

- `self.robot.move_relative`
- `self.robot.set_speed`
- `self.robot.home`
- `self.robot.stop`

The tools send HTTP POST requests to the C# RobotAnno API.

Current Robot API base URL:

`http://192.168.80.144:5000`

To change the robot PC address, edit:

`main/robot_http_config.h`

Example voice intents:

- "trục 1 lên 10 độ" -> `self.robot.move_relative(j1=10)`
- "trục 1 lên 10 độ, trục 3 xuống 5 độ" -> `j1=10, j3=-5`
- "đặt tốc độ robot 5 phần trăm" -> `self.robot.set_speed(vp=5)`
- "đưa robot về home" -> `self.robot.home()`
- "dừng robot" -> `self.robot.stop()`

C# endpoints expected:

- `POST /robot/move`
- `POST /robot/speed`
- `POST /robot/home`
- `POST /robot/stop`

The robot PC and ESP must be mutually reachable over the network.
