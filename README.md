# SmartCar 智能视觉追踪小车系统

This is an Arduino-based intelligent vision tracking car system that uses the XIAO development board as the main controller and controls the car's movement through I2C communication with the receiver Arduino.
这是一个基于Arduino的智能视觉追踪小车系统，使用XIAO开发板作为主控制器，通过I2C通信控制接收端Arduino来控制小车运动。

## System Components 系统组成

### Hardware Requirements 硬件要求
- XIAO Development Board (Main Controller)
  - XIAO开发板（主控制器）
- Arduino UNO/NANO (Receiver Controller)
  - Arduino UNO/NANO（接收端控制器）
- Grove Vision AI Module
  - Grove Vision AI模块
- Mecanum Wheel Chassis
  - 麦克纳姆轮小车底盘
- Motor Driver Module
  - 电机驱动模块
- 4 DC Motors
  - 4个直流电机

### Software Dependencies 软件依赖
- Arduino IDE
  - Arduino IDE
- Wire Library
  - Wire库
- Seeed_Arduino_SSCMA Library
  - Seeed_Arduino_SSCMA库

## Features 功能特点

1. **Vision Recognition 视觉识别功能**
   - Real-time target detection 实时目标检测
   - Position determination (left, center, right) 位置判断（左、中、右）
   - Distance estimation (far, near) 距离估算（远、近）

2. **Motion Control 运动控制功能**
   - In-place left turn 原地左转
   - In-place right turn 原地右转
   - Forward movement 直行前进
   - Stop 停止

3. **Intelligent Tracking 智能追踪**
   - Automatic target tracking 自动追踪目标
   - Timeout protection mechanism 超时保护机制
   - Real-time position adjustment 实时位置调整

## System Architecture 系统架构

### Main Controller (XIAO) 主控制器（XIAO）
- Responsible for vision recognition 负责视觉识别
- Processes target position information 处理目标位置信息
- Sends control commands via I2C 通过I2C发送控制命令

### Receiver (Arduino) 接收端（Arduino）
- Receives I2C control commands 接收I2C控制命令
- Controls motor movement 控制电机运动
- Implements Mecanum wheel kinematics control 实现麦克纳姆轮运动学控制

## Communication Protocol 通信协议

The system uses I2C communication with the following protocol:
系统使用I2C通信，通信协议如下：
- Command 1: In-place left turn  命令1：原地左转
- Command 2: In-place right turn 命令2：原地右转
- Command 3: Stop              命令3：停止
- Command 4: Forward movement  命令4：直行前进

## Parameter Configuration 参数配置

### Vision Parameters 视觉参数
- Left boundary: x < 150         左边界：x < 150
- Right boundary: x > 345        右边界：x > 345
- Center area: 150 ≤ x ≤ 345     中心区域：150 ≤ x ≤ 345
- Distance threshold: 230000 (area) 距离判断阈值：230000（面积）

### Motion Parameters 运动参数
- Forward speed: 80              直行速度：80
- Turning speed: 70              转向速度：70
- Detection interval: 50ms       检测间隔：50ms
- Timeout duration: 3000ms       超时时间：3000ms

## Usage Instructions 使用说明

1. Upload the code to XIAO and Arduino development boards respectively
   将代码分别上传到XIAO和Arduino开发板
2. Ensure correct I2C connection (XIAO as master, Arduino as slave, address 8)
   确保I2C连接正确（XIAO作为主机，Arduino作为从机，地址为8）
3. System starts working automatically after power-on
   上电后系统自动开始工作
4. System will automatically track targets in view
   系统会自动追踪视野中的目标

## Precautions 注意事项

1. Ensure correct motor wiring
   确保电机接线正确
2. Check I2C connection stability
   检查I2C连接是否稳定
3. Ensure adequate power supply
   注意电源供应充足
4. Regularly check motor operation status
   定期检查电机运行状态

## Debug Information 调试信息

The system outputs the following debug information through serial port:
系统会通过串口输出以下调试信息：
- Target position 目标位置
- Coordinate information 坐标信息
- Distance information 距离信息
- Confidence level 置信度
- Control commands 控制命令

## Maintenance Recommendations 维护建议

1. Regularly clean the camera lens
   定期清洁摄像头镜头
2. Check motor operation status
   检查电机运行状态
3. Ensure sufficient battery power
   确保电池电量充足
4. Regularly check wiring connections
   定期检查接线连接 
