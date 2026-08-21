# Ex.No.4-EXP 4 Generate the Prompt and evaluate that for following prompt patterns - Zero-shot Prompting.•	Few-shot Prompting - Chain of Thought -	Persona Pattern - Reverse Prompting - Graph Prompting - Active Prompting
### DATE: 21-08-2026                                                                         
### REGISTER NUMBER : 212223230143
### Aim:
To write the prompt for the following prompt types and compare that with different AI tools and evaluate that using any one evaluation method (Ex. Rubrics). Zero-shot Prompting.•	Few-shot Prompting - Chain of Thought -	Persona Pattern - Reverse Prompting - Graph Prompting - Active Prompting 

### Explanation - Use engineering case studies such as - Smart Irrigation, Drone Navigation, Robot Path P

# Prompt Engineering Using Engineering Case Studies

## 1. Introduction

Prompt engineering is the process of designing effective instructions for Large Language Models (LLMs) to obtain useful, accurate, and relevant responses.

This experiment explores seven prompt engineering methods by applying them to three engineering applications:

* Smart Irrigation System
* Autonomous Drone Navigation
* Robot Path Planning

The techniques studied are:

1. Zero-shot Prompting
2. Few-shot Prompting
3. Chain-of-Thought Prompting
4. Persona Pattern
5. Reverse Prompting
6. Graph Prompting
7. Active Prompting

The outputs are compared using three evaluation parameters:

* Reasoning Quality
* Correctness
* Token Usage

---

# 2. Objectives

The objectives of this experiment are:

* To understand different prompt engineering techniques.
* To create prompts for practical engineering problems.
* To study the effect of prompt structure on LLM responses.
* To compare the reasoning ability of different prompting approaches.
* To evaluate the correctness of generated engineering solutions.
* To analyze token consumption.
* To determine which prompting method is appropriate for different engineering applications.

---

# 3. Engineering Problems

## 3.1 Smart Irrigation

### Problem

Develop an automated irrigation system that decides when irrigation should start based on soil moisture, temperature, humidity, crop requirements, weather conditions, and available water.

### Expected System

The system should:

* Monitor environmental conditions.
* Determine crop water requirements.
* Predict whether irrigation is necessary.
* Control the water pump automatically.
* Avoid unnecessary water consumption.

---

## 3.2 Autonomous Drone Navigation

### Problem

Develop a navigation system for a drone that travels between two locations while avoiding obstacles and considering distance, battery consumption, and flight safety.

### Expected System

The system should:

* Determine the drone's position.
* Detect obstacles.
* Generate a safe route.
* Recalculate the route when necessary.
* Monitor battery status.

---

## 3.3 Robot Path Planning

### Problem

Develop a navigation and path-planning solution for a warehouse robot that moves between locations while avoiding both permanent and moving obstacles.

### Expected System

The system should:

* Represent the warehouse environment.
* Find an efficient route.
* Detect obstacles.
* Replan when obstacles appear.
* Maintain a safe distance from objects.

---

# 4. Zero-shot Prompting

## Definition

Zero-shot prompting asks the model to solve a problem without giving any examples.

---

## 4.1 Smart Irrigation

### Prompt

```text
Develop an automated irrigation solution for a crop field.

The system should consider soil moisture, temperature, humidity, rainfall prediction, crop type, and water availability.

Explain how the system can decide whether irrigation is needed and how the water pump can be controlled.
```

### Output

```text
An automated irrigation system can collect information from environmental sensors and use the data to determine irrigation requirements.

The system can use soil moisture sensors, temperature sensors, humidity sensors, and weather forecast information.

The controller compares the current soil moisture with the required moisture level for the crop. If the moisture is below the required level and rainfall is unlikely, the controller activates the water pump.

The pump can be controlled using a relay connected to a microcontroller.

A water-level sensor can also be used to prevent the pump from operating when sufficient water is unavailable.

The system helps conserve water, reduce manual effort, and maintain suitable soil conditions for crops.
```

---

## 4.2 Drone Navigation

### Prompt

```text
Propose an autonomous navigation system for a drone that must travel from a source location to a destination while avoiding obstacles and reducing unnecessary battery consumption.

Mention suitable sensors, path-planning methods, and safety mechanisms.
```

### Output

```text
A drone navigation system can combine GPS, IMU, camera or LiDAR sensors, and a path-planning algorithm.

GPS can provide the drone's global position, while the IMU measures orientation and motion.

Camera or LiDAR sensors can identify obstacles in the drone's surroundings.

A path-planning algorithm such as A* can generate an efficient route. When an obstacle is detected, the system can calculate a new route.

Battery monitoring should be included so that the drone does not select a route that requires more energy than is available.

Safety features can include collision avoidance, geofencing, emergency landing, and return-to-home functionality.
```

---

## 4.3 Robot Path Planning

### Prompt

```text
Create a path-planning solution for a warehouse robot that needs to move from one location to another while avoiding static and moving obstacles.

Explain the path-planning algorithm, sensors, and safety mechanism.
```

### Output

```text
The warehouse can be represented as an occupancy grid containing free and occupied regions.

A* can be used to calculate an efficient route between the starting and destination positions.

LiDAR or cameras can detect obstacles while the robot is moving.

If a dynamic obstacle blocks the planned route, the robot can slow down or stop and calculate a new route.

The robot should maintain a safe distance from obstacles and should stop if no safe route is available.
```

---

# 5. Few-shot Prompting

## Definition

Few-shot prompting provides examples to the model before asking it to solve a new problem.

---

## 5.1 Smart Irrigation

### Prompt

```text
Example 1:

Condition:
Soil moisture = 18%
Rain probability = 10%

Decision:
Start irrigation because the soil is dry and rainfall is unlikely.

Example 2:

Condition:
Soil moisture = 70%
Rain probability = 85%

Decision:
Do not irrigate because the soil already has sufficient moisture and rainfall is expected.

New condition:

Soil moisture = 32%
Temperature = 35°C
Rain probability = 12%
Crop = Groundnut

Should irrigation be started? Explain your answer.
```

### Output

```text
Irrigation should be started.

The soil moisture level of 32% indicates that the field may require additional water. The temperature of 35°C can increase evaporation and water demand.

The rainfall probability is only 12%, so significant natural rainfall is unlikely.

Therefore, controlled irrigation should be started. The exact quantity of water should depend on soil characteristics, crop growth stage, field size, and available water.
```

---

## 5.2 Drone Navigation

### Prompt

```text
Example 1:

Situation:
The drone has a clear path and sufficient battery.

Decision:
Use the shortest safe route.

Example 2:

Situation:
An obstacle is detected directly ahead.

Decision:
Avoid the obstacle and calculate an alternative safe route.

New situation:

The drone has 55% battery remaining. The shortest route contains two obstacles, while another route is 10% longer and has no detected obstacles.

Select the preferred route and justify your decision.
```

### Output

```text
The safer alternative route should be preferred if its estimated energy requirement is within the available battery capacity.

Although the route is 10% longer, it avoids the two detected obstacles and therefore reduces collision risk and unnecessary emergency manoeuvres.

The drone should estimate the energy requirement of the alternative route before selecting it and continue monitoring battery status during flight.
```

---

## 5.3 Robot Path Planning

### Prompt

```text
Example 1:

A robot has an obstacle-free map.
Decision:
Use A* to calculate an efficient path.

Example 2:

A permanent obstacle blocks the shortest path.
Decision:
Recalculate the route around the obstacle.

Example 3:

A moving object blocks the current route.
Decision:
Stop or slow down and calculate a new route.

New situation:

A warehouse robot detects a moving worker directly along its planned route using LiDAR.

What should the robot do?
```

### Output

```text
The robot should immediately reduce its speed and stop if necessary.

LiDAR information should be used to update the local environment representation. The path planner should then generate a new collision-free route.

The robot should continue only after confirming that the new route provides an appropriate safety margin.

Process:

Detect → Slow/Stop → Update Environment → Replan → Check Safety → Continue
```

---

# 6. Chain-of-Thought Prompting

## Definition

This technique requests a structured analysis of the factors involved in a problem before reaching a conclusion.

For this experiment, evaluation focuses on the quality of the explanation and final recommendation rather than requiring private internal reasoning.

---

## 6.1 Smart Irrigation

### Prompt

```text
Analyze the following irrigation scenario in a structured manner.

Soil moisture = 25%
Temperature = 36°C
Humidity = 38%
Rain probability = 20%
Crop = Maize

Evaluate each factor and determine whether irrigation should be activated.

Provide the important reasoning factors followed by the final recommendation.
```

### Output

```text
Soil Moisture:
The moisture level is 25%, indicating relatively dry soil and a possible need for irrigation.

Temperature:
The temperature is 36°C, which can increase evaporation and crop water requirements.

Humidity:
Humidity is 38%, which is relatively low and may contribute to increased water loss.

Rainfall:
Rain probability is only 20%, so rainfall cannot be relied upon to satisfy the crop's immediate water requirement.

Crop:
Maize requires appropriate moisture for healthy growth, although the exact threshold depends on the growth stage and soil.

Recommendation:
Irrigation should be considered. The irrigation quantity should be determined using crop growth stage, soil type, field size, and water availability.
```

---

## 6.2 Drone Navigation

### Prompt

```text
Evaluate the following drone navigation problem systematically.

A drone has 70% battery. The direct path is shorter but contains several obstacles. A second route is 18% longer and has considerably lower obstacle risk.

Consider distance, energy, obstacle risk, and safety before recommending a route.
```

### Output

```text
Battery:
The drone has 70% battery, providing a reasonable energy reserve.

Direct Route:
The direct route minimizes distance but contains several obstacles, increasing collision and replanning risk.

Alternative Route:
The second route requires approximately 18% more distance but has lower obstacle risk.

Energy:
The drone should estimate whether the additional distance can be completed while maintaining an appropriate battery reserve.

Safety:
Avoiding obstacles should receive high priority during autonomous navigation.

Recommendation:
The alternative route should be selected if its estimated energy consumption is within the drone's safe battery budget.
```

---

## 6.3 Robot Path Planning

### Prompt

```text
Analyze this warehouse robot problem step by step.

A robot must travel from point A to point B. The initial route contains a fixed obstacle. During movement, another moving obstacle may appear.

Discuss:
1. Map representation
2. Route generation
3. Obstacle detection
4. Dynamic replanning
5. Safety

Then give the recommended solution.
```

### Output

```text
Map Representation:
An occupancy grid or graph can represent the warehouse environment.

Route Generation:
A* can be used to calculate an efficient initial route while avoiding known obstacles.

Obstacle Detection:
LiDAR or camera sensors can detect objects that are not included in the original map.

Dynamic Replanning:
When a moving obstacle blocks the route, the local environment should be updated and a new path should be calculated.

Safety:
The robot should maintain an appropriate clearance from obstacles and reduce its speed near people or vehicles.

Recommended Solution:
Use A* for global route planning together with real-time obstacle detection and local path replanning.
```

---

# 7. Persona Pattern

## Definition

Persona prompting assigns a professional role to the AI before requesting the solution.

---

## 7.1 Smart Irrigation

### Prompt

```text
Act as a precision agriculture and IoT engineer.

Design a smart irrigation system using environmental sensors and intelligent decision-making.

Include:
- Sensors
- System architecture
- Irrigation logic
- Hardware control
- Safety features
- Advantages
```

### Output

```text
As a precision agriculture and IoT engineer, I would design the system as a sensor-driven closed-loop irrigation system.

Architecture:

Environmental Sensors
        ↓
Microcontroller
        ↓
Data Processing
        ↓
Irrigation Decision
        ↓
Pump Controller
        ↓
Water Pump
        ↓
Agricultural Field
        ↓
Soil Moisture Feedback

Required sensors include soil moisture, temperature, humidity, and water-level sensors. Weather forecast data can also be obtained through an online API.

The controller compares soil moisture against a crop-specific threshold. It also considers predicted rainfall and water availability.

Safety mechanisms should include maximum pump duration, low-water detection, sensor fault detection, and manual override.

The system can reduce water consumption while providing automated crop irrigation.
```

---

## 7.2 Drone Navigation

### Prompt

```text
Act as a UAV systems engineer with experience in autonomous navigation, computer vision, sensor fusion, and path planning.

Design a reliable drone navigation architecture for obstacle avoidance and battery-aware route planning.
```

### Output

```text
A reliable UAV navigation system can be divided into the following layers:

Perception:
- Camera
- LiDAR
- GPS
- IMU

Localization:
Sensor fusion can combine GPS, IMU, and visual or LiDAR information to estimate the drone's position.

Planning:
A global planner can calculate the overall route, while a local planner can react to nearby obstacles.

Control:
The flight controller converts navigation decisions into movement commands.

Energy Management:
Battery state should be continuously monitored and considered during route selection.

Safety:
The system should support collision avoidance, geofencing, emergency landing, and return-to-home procedures.

This layered design allows perception, localization, planning, control, and safety functions to work together.
```

---

## 7.3 Robot Path Planning

### Prompt

```text
Act as a mobile robotics engineer specializing in autonomous warehouse robots.

Develop a navigation architecture capable of handling both permanent and moving obstacles.

Mention suitable mapping, localization, planning, sensing, and safety methods.
```

### Output

```text
A warehouse robot can use a hierarchical navigation system.

Mapping:
An existing warehouse map or SLAM can represent the environment.

Localization:
LiDAR, wheel odometry, and IMU can be combined to estimate the robot's position.

Global Planning:
A* or Dijkstra can calculate an efficient route.

Local Planning:
Real-time sensor information can be used to avoid dynamic obstacles.

Replanning:
The route should be recalculated when the environment changes.

Safety:
The robot should maintain obstacle clearance, control its speed, and stop when safe navigation is impossible.

This architecture provides efficient global navigation while allowing real-time responses to unexpected obstacles.
```

---

# 8. Reverse Prompting

## Definition

Reverse prompting starts by identifying the information required to solve a problem before generating the actual solution.

---

## 8.1 Smart Irrigation

### Prompt

```text
Before designing a smart irrigation system, identify the most important information that must be collected about the farm, crop, soil, climate, water source, sensors, and operating conditions.

After identifying the requirements, provide a suitable system design.
```

### Output

```text
Important requirements include:

Farm:
- Farm size
- Number of irrigation zones
- Existing irrigation infrastructure

Crop:
- Crop type
- Growth stage
- Required moisture range

Soil:
- Soil type
- Water retention characteristics
- Current moisture

Climate:
- Temperature
- Humidity
- Expected rainfall
- Weather conditions

Water:
- Water source
- Available quantity
- Pump capacity

Technology:
- Available sensors
- Communication method
- Controller hardware

Proposed Design:

Sensors can send environmental information to a microcontroller. The controller can combine sensor data with weather information and crop-specific requirements.

An irrigation algorithm can determine the required irrigation duration and activate the pump through a relay.

The system should include water-level monitoring, maximum irrigation limits, and manual control.
```

---

## 8.2 Drone Navigation

### Prompt

```text
Before designing the drone navigation system, identify the important requirements related to the drone, operating environment, sensors, obstacles, battery, communication, and safety.

After identifying these requirements, suggest a general navigation architecture.
```

### Output

```text
Important requirements include:

- Drone type and payload
- Maximum flight duration
- GPS availability
- Operating altitude
- Indoor or outdoor environment
- Static or moving obstacles
- Available sensors
- Required navigation accuracy
- Maximum speed
- Communication range
- Battery capacity
- Emergency procedures

Architecture:

Sensors
   ↓
Perception
   ↓
Localization
   ↓
Global Planning
   ↓
Local Planning
   ↓
Flight Control

Battery and safety monitoring should operate throughout the navigation process.
```

---

## 8.3 Robot Path Planning

### Prompt

```text
Before choosing a path-planning algorithm for a warehouse robot, determine the important requirements concerning the warehouse map, obstacles, robot speed, sensors, localization, multiple robots, and safety.

Then suggest a suitable architecture.
```

### Output

```text
Important questions:

1. Is a warehouse map already available?
2. Are obstacles static, dynamic, or both?
3. Are humans present in the operating area?
4. Which sensors are available?
5. What is the maximum robot speed?
6. How quickly must obstacles be detected?
7. How accurate must localization be?
8. Are multiple robots operating?
9. Is shortest distance or minimum travel time more important?
10. What safety constraints are required?

Suggested architecture:

Sensors → Localization → Environment Model → Global Planner → Local Planner → Controller

A* can be considered for global path planning, with real-time local replanning for dynamic obstacles.
```

---

# 9. Graph Prompting

## Definition

Graph prompting models an engineering system as nodes and connections. It is useful for understanding component relationships and information flow.

---

## 9.1 Smart Irrigation

### Prompt

```text
Represent a smart irrigation system as a directed graph.

Use these components:

Soil Moisture
Temperature
Humidity
Weather Service
Crop Information
Water Availability
Decision Module
Pump Controller
Water Pump
Crop Field

Show the information flow and explain how the feedback loop works.
```

### Output

```text
Soil Moisture ────────┐
Temperature ──────────┤
Humidity ─────────────┤
Weather Service ──────┤
Crop Information ─────┤
Water Availability ───┤
                      ↓
                Decision Module
                      ↓
                Pump Controller
                      ↓
                  Water Pump
                      ↓
                  Crop Field
                      ↓
                Soil Moisture

The sensors and external weather information provide data to the decision module.

Crop information determines the required moisture level. Water availability determines whether irrigation can be performed.

The decision module sends an instruction to the pump controller. The pump supplies water to the field.

After irrigation, soil moisture changes and is measured again, creating a feedback loop.
```

---

## 9.2 Drone Navigation

### Prompt

```text
Create a graph representation of an autonomous drone navigation system using these nodes:

GPS
IMU
Camera
LiDAR
Localization
Obstacle Detection
Route Planner
Local Avoidance
Battery Monitor
Flight Controller
Destination

Explain the relationships between the nodes.
```

### Output

```text
GPS ────────────────┐
                    ↓
IMU ───────────> Localization
                    ↑
Camera ──> Obstacle Detection <── LiDAR
                    │
                    ↓
                Route Planner
                    │
                    ↓
               Local Avoidance
                    ↑
                    │
              Battery Monitor
                    │
                    ↓
             Flight Controller
                    │
                    ↓
                Destination

GPS and IMU provide positioning information.

Camera and LiDAR provide information about obstacles.

The route planner generates the overall route, while local avoidance modifies the route when an obstacle is detected.

The battery monitor ensures that the route remains feasible.
```

---

## 9.3 Robot Path Planning

### Prompt

```text
Represent a warehouse robot navigation system using a directed graph.

Nodes:
Warehouse Map
Robot Position
LiDAR
Camera
Obstacle Detection
Global Planner
Local Planner
Safety Module
Motor Controller
Destination

Explain the information flow.
```

### Output

```text
Warehouse Map ────────┐
                      ↓
Robot Position ──> Global Planner
                      │
                      ↓
                  Local Planner
                      ↑
                      │
LiDAR ──> Obstacle Detection <── Camera
                      │
                      ↓
                 Safety Module
                      │
                      ↓
                Motor Controller
                      │
                      ↓
                  Destination

The warehouse map and robot position are used to generate a global route.

LiDAR and camera sensors detect obstacles.

The local planner modifies the route when obstacles are detected.

The safety module checks whether the movement is safe before commands are sent to the motor controller.
```

---

# 10. Active Prompting

## Definition

Active prompting allows the model to ask the user for high-value information before generating a final solution.

---

## 10.1 Smart Irrigation

### Prompt

```text
You are designing a smart irrigation system.

Do not immediately propose a solution.

First ask the most important questions whose answers could significantly affect the hardware, irrigation strategy, or software architecture.

Ask only high-priority questions.
```

### Output

```text
The most important questions are:

1. What crop is being cultivated?
2. What is the approximate field size?
3. What type of soil is present?
4. What is the available water source?
5. How much water is available per day?
6. Is weather forecast data available?
7. What sensors are already installed?
8. What level of automation is required?

These answers will determine the irrigation thresholds, sensor requirements, pump capacity, communication system, and control algorithm.
```

---

## 10.2 Drone Navigation

### Prompt

```text
You are designing an autonomous drone navigation system.

Before selecting the navigation algorithm, ask the minimum number of important questions required to understand the operating environment, sensors, obstacles, battery constraints, and safety requirements.

Do not make assumptions about missing information.
```

### Output

```text
Important questions:

1. Will the drone operate indoors or outdoors?
2. Is GPS available throughout the flight?
3. Are obstacles static, dynamic, or both?
4. Which sensors are available?
5. What is the required navigation accuracy?
6. What is the maximum flight time?
7. What is the maximum operating speed?
8. Is real-time obstacle avoidance required?
9. What onboard computing hardware is available?
10. What emergency procedures are required?

These answers are required to select appropriate perception, localization, planning, and control methods.
```

---

## 10.3 Robot Path Planning

### Prompt

```text
You are developing a navigation system for a warehouse robot.

Before selecting a path-planning algorithm, ask the critical questions needed to determine the map representation, sensors, obstacle behavior, robot constraints, and safety requirements.

Avoid making assumptions that could affect the final architecture.
```

### Output

```text
Critical questions:

1. Is a complete warehouse map available?
2. Are there moving obstacles?
3. Will humans work near the robot?
4. What sensors are installed?
5. What is the robot's maximum speed?
6. What is the required reaction time?
7. How accurate is the localization system?
8. Are multiple robots operating in the warehouse?
9. Is the objective shortest distance, shortest time, or minimum energy?
10. What safety requirements must be followed?

The answers will determine the mapping, sensing, planning, and collision-avoidance strategy.
```

---

# 11. Evaluation Criteria

The generated responses are evaluated using three metrics.

## Reasoning Quality

Reasoning evaluates whether the model considers relevant engineering factors and connects them logically.

| Score | Description                      |
| ----: | -------------------------------- |
|     5 | Highly logical and comprehensive |
|     4 | Logical with minor omissions     |
|     3 | Adequate                         |
|     2 | Limited reasoning                |
|     1 | Poor or irrelevant reasoning     |

## Correctness

Correctness evaluates whether the proposed engineering solution is technically appropriate.

| Score | Description           |
| ----: | --------------------- |
|     5 | Fully correct         |
|     4 | Mostly correct        |
|     3 | Partially correct     |
|     2 | Contains major issues |
|     1 | Incorrect             |

## Token Usage

Token usage measures the number of tokens required to produce the response.

The total number of tokens is:

```text
Total Tokens = Input Tokens + Output Tokens
```

A useful quality-efficiency measure is:

```text
Quality Efficiency = (Reasoning Score + Correctness Score) / Total Tokens
```

A higher value indicates better quality relative to token consumption.

---

# 12. Evaluation Results

The following values are illustrative and should be replaced with actual measurements obtained from the selected LLM.

| Prompting Method  | Reasoning /5 | Correctness /5 | Token Efficiency /5 |
| ----------------- | -----------: | -------------: | ------------------: |
| Zero-shot         |            3 |              4 |                   5 |
| Few-shot          |            4 |              4 |                   4 |
| Chain-of-Thought  |            5 |              5 |                   2 |
| Persona           |            4 |              5 |                   3 |
| Reverse Prompting |            5 |              5 |                   3 |
| Graph Prompting   |            5 |              5 |                   3 |
| Active Prompting  |            5 |              5 |                   3 |

---

# 13. Result Analysis

### Zero-shot Prompting

Zero-shot prompting produced relatively concise answers with good token efficiency. However, some responses lacked detailed engineering constraints.

### Few-shot Prompting

Few-shot prompting improved consistency because the examples demonstrated the desired decision-making pattern. Its main disadvantage was the additional token cost of providing examples.

### Chain-of-Thought Prompting

Structured reasoning produced detailed and logically organized answers. It was particularly effective for problems involving multiple engineering constraints. However, the resulting responses were generally longer.

### Persona Pattern

Persona prompting generated more domain-specific responses. For example, the robotics persona introduced concepts such as localization, sensor fusion, global planning, and local planning.

### Reverse Prompting

Reverse prompting was effective for requirements engineering. Instead of immediately proposing a solution, it identified missing information that could affect the design.

### Graph Prompting

Graph prompting was useful for representing relationships between system components. It clearly showed information flow and feedback mechanisms.

### Active Prompting

Active prompting was useful when the initial problem statement was incomplete. It allowed the model to identify high-impact questions before selecting an architecture.

---

# 14. Comparative Summary

| Technique        | Major Advantage             | Major Limitation                   | Suitable Application     |
| ---------------- | --------------------------- | ---------------------------------- | ------------------------ |
| Zero-shot        | Low token usage             | Generic responses                  | Simple problems          |
| Few-shot         | Consistent outputs          | More input tokens                  | Pattern-based tasks      |
| Chain-of-Thought | Detailed reasoning          | Higher token usage                 | Complex analysis         |
| Persona          | Domain-specific answers     | Extra context                      | Expert engineering tasks |
| Reverse          | Finds missing requirements  | May require interaction            | Requirements analysis    |
| Graph            | Shows relationships clearly | Requires structured representation | System architecture      |
| Active           | Handles uncertainty         | Interactive                        | Incomplete problems      |

---

# 15. Key Findings

1. Prompt structure significantly affects the quality of LLM-generated engineering solutions.

2. Zero-shot prompting is effective when a quick and concise answer is required.

3. Few-shot prompting improves consistency when examples represent the expected behavior.

4. Chain-of-Thought-style prompts are useful for multi-factor engineering decisions.

5. Persona prompts improve domain relevance.

6. Reverse prompting is useful for discovering missing requirements.

7. Graph prompting helps visualize component dependencies and information flow.

8. Active prompting is useful when the available requirements are incomplete.

9. More detailed prompts can improve reasoning but generally increase token consumption.

10. The best prompting strategy depends on the specific engineering problem and the desired balance between quality and efficiency.

---

# 16. Conclusion

This experiment explored seven prompt engineering techniques using three engineering applications: Smart Irrigation, Drone Navigation, and Robot Path Planning.

The comparison demonstrates that different prompting methods have different strengths. Zero-shot prompting provides a simple baseline, while few-shot prompting improves consistency through examples. Chain-of-Thought-style prompting supports structured analysis, whereas Persona Pattern provides domain-oriented responses.

Reverse Prompting and Active Prompting are particularly valuable when requirements are incomplete because they encourage identification of missing information. Graph Prompting is effective for engineering systems where several components interact with each other.

Overall, prompt engineering provides an effective way to control the structure, relevance, and quality of AI-generated engineering solutions. However, increased prompt complexity can also increase token usage. Therefore, an effective prompt should balance **reasoning quality, correctness, and token efficiency**.

---

# Final Takeaway

```text
                 Prompt Engineering
                        │
        ┌───────────────┼────────────────┐
        │               │                │
     Prompt          Context         Interaction
        │               │                │
   Zero-shot        Few-shot          Active
   CoT              Persona           Reverse
   Graph
        │               │                │
        └───────────────┼────────────────┘
                        ↓
              Engineering Solution
                        ↓
          ┌─────────────┼─────────────┐
          ↓             ↓             ↓
      Reasoning     Correctness    Token Usage
          │             │             │
          └─────────────┼─────────────┘
                        ↓
                  Final Evaluation
```

> **Effective prompt engineering is not about using the longest prompt; it is about providing the right instructions, context, examples, and interaction strategy for the specific problem.**

---

# Result: 
The various types of Prompts are executed successfully with generated the report.
