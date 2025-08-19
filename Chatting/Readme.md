# ROS 환경 Chatting Topic

## 실행 환경

| 항목         | 내용                  |
|------------|-------------------|
| OS         | Ubuntu 20.04        |
| ROS 버전    | Noetic (Python3 기반) |
| Python 버전 | 3.x                 |
| 워크스페이스 | `~/catkin_ws`       |
| 필수 패키지 | `rospy`, `std_msgs` |

## 동작 과정

1. roscore 실행 → ROS Master가 구동되어 토픽과 노드 연결 정보 관리
2. listener.py 실행 → `'chatter'` 토픽 구독(Subsriber 등록)
3. talker.py 실행 → `'chatter'` 토픽으로 메시지 발행(Publisher 등록)
4. 메시지 전달 및 수신 → Publisher가 발행한 메시지가 Subscriber로 직접 전송되고, 콜백 함수에서 콘솔에 출력

## 구조도
+----------------+
| roscore |
| ROS Master |
| 토픽/노드 정보 |
+--------+-------+
|
연결 정보 제공
v
+----------------+ chatter +----------------+
| talker.py | ------------------> | listener.py |
| Publisher | (직접 전송) | Subscriber |
| "Hello ROS!" | | print received |
+----------------+ +----------------+


