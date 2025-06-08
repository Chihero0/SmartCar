# SmartCar
# Intelligent Vision Tracking Car System

This is an Arduino-based intelligent vision tracking car system that uses the XIAO development board as the main controller and controls the car's movement through I2C communication with the receiver Arduino.

## System Components

### Hardware Requirements
- XIAO Development Board (Main Controller)
- Arduino UNO/NANO (Receiver Controller)
- Grove Vision AI Module
- Mecanum Wheel Chassis
- Motor Driver Module
- 4 DC Motors

### Software Dependencies
- Arduino IDE
- Wire Library
- Seeed_Arduino_SSCMA Library

## Features

1. **Vision Recognition**
   - Real-time target detection
   - Position determination (left, center, right)
   - Distance estimation (far, near)

2. **Motion Control**
   - In-place left turn
   - In-place right turn
   - Forward movement
   - Stop

3. **Intelligent Tracking**
   - Automatic target tracking
   - Timeout protection mechanism
   - Real-time position adjustment

## System Architecture

### Main Controller (XIAO)
- Responsible for vision recognition
- Processes target position information
- Sends control commands via I2C

### Receiver (Arduino)
- Receives I2C control commands
- Controls motor movement
- Implements Mecanum wheel kinematics control

## Communication Protocol

The system uses I2C communication with the following protocol:
- Command 1: In-place left turn
- Command 2: In-place right turn
- Command 3: Stop
- Command 4: Forward movement

## Parameter Configuration

### Vision Parameters
- Left boundary: x < 150
- Right boundary: x > 345
- Center area: 150 ≤ x ≤ 345
- Distance threshold: 230000 (area)

### Motion Parameters
- Forward speed: 80
- Turning speed: 70
- Detection interval: 50ms
- Timeout duration: 3000ms

## Usage Instructions

1. Upload the code to XIAO and Arduino development boards respectively
2. Ensure correct I2C connection (XIAO as master, Arduino as slave, address 8)
3. System starts working automatically after power-on
4. System will automatically track targets in view

## Precautions

1. Ensure correct motor wiring
2. Check I2C connection stability
3. Ensure adequate power supply
4. Regularly check motor operation status

## Debug Information

The system outputs the following debug information through serial port:
- Target position
- Coordinate information
- Distance information
- Confidence level
- Control commands

## Maintenance Recommendations

1. Regularly clean the camera lens
2. Check motor operation status
3. Ensure sufficient battery power
4. Regularly check wiring connections 
# 智能视觉追踪小车系统

这是一个基于Arduino的智能视觉追踪小车系统，使用XIAO开发板作为主控制器，通过I2C通信控制接收端Arduino来控制小车运动。

## 系统组成

### 硬件要求
- XIAO开发板（主控制器）
- Arduino UNO/NANO（接收端控制器）
- Grove Vision AI模块
- 麦克纳姆轮小车底盘
- 电机驱动模块
- 4个直流电机

### 软件依赖
- Arduino IDE
- Wire库
- Seeed_Arduino_SSCMA库

## 功能特点

1. **视觉识别功能**
   - 实时目标检测
   - 位置判断（左、中、右）
   - 距离估算（远、近）

2. **运动控制功能**
   - 原地左转
   - 原地右转
   - 直行前进
   - 停止

3. **智能追踪**
   - 自动追踪目标
   - 超时保护机制
   - 实时位置调整

## 系统架构

### 主控制器（XIAO）
- 负责视觉识别
- 处理目标位置信息
- 通过I2C发送控制命令

### 接收端（Arduino）
- 接收I2C控制命令
- 控制电机运动
- 实现麦克纳姆轮运动学控制

## 通信协议

系统使用I2C通信，通信协议如下：
- 命令1：原地左转
- 命令2：原地右转
- 命令3：停止
- 命令4：直行前进

## 参数配置

### 视觉参数
- 左边界：x < 150
- 右边界：x > 345
- 中心区域：150 ≤ x ≤ 345
- 距离判断阈值：230000（面积）

### 运动参数
- 直行速度：80
- 转向速度：70
- 检测间隔：50ms
- 超时时间：3000ms

## 使用说明

1. 将代码分别上传到XIAO和Arduino开发板
2. 确保I2C连接正确（XIAO作为主机，Arduino作为从机，地址为8）
3. 上电后系统自动开始工作
4. 系统会自动追踪视野中的目标

## 注意事项

1. 确保电机接线正确
2. 检查I2C连接是否稳定
3. 注意电源供应充足
4. 定期检查电机运行状态

## 调试信息

系统会通过串口输出以下调试信息：
- 目标位置
- 坐标信息
- 距离信息
- 置信度
- 控制命令

## 维护建议

1. 定期清洁摄像头镜头
2. 检查电机运行状态
3. 确保电池电量充足
4. 定期检查接线连接 
