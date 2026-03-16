# ROS2 Fundamentals Workspace

**Version**: 1.0  
**Status**: Educational/Reference  
**ROS2 Distro**: Jazzy  
**Purpose**: Learning and testing ROS2 core concepts

A workspace dedicated to learning ROS2 fundamentals and testing core middleware concepts.

## Contents

```
ros2_ws/
├── src/
│   └── ros2_fundamentals_examples/    Example packages for core ROS2 concepts
├── build/
├── install/
├── log/
└── README.md
```

## Packages

### `ros2_fundamentals_examples`

Educational examples covering:
- **Nodes**: Creating publishers and subscribers
- **Topics**: Message passing patterns (pub/sub)
- **Services**: Request/response patterns
- **Actions**: Long-running asynchronous tasks
- **Parameters**: Dynamic configuration
- **Launch files**: Multi-node orchestration
- **Transformations (TF2)**: Coordinate frame management
- **Quality of Service (QoS)**: Message reliability settings

## Quick Start

### Build
```bash
cd ~/ros2_ws
colcon build --symlink-install
```

### Source Environment
```bash
source install/setup.bash
```

### Run Examples

**Minimal Publisher/Subscriber:**
```bash
ros2 run ros2_fundamentals_examples talker
# In another terminal:
ros2 run ros2_fundamentals_examples listener
```

**Service Example:**
```bash
ros2 run ros2_fundamentals_examples service_server
# In another terminal:
ros2 run ros2_fundamentals_examples service_client
```

**Action Example:**
```bash
ros2 run ros2_fundamentals_examples action_server
# In another terminal:
ros2 run ros2_fundamentals_examples action_client
```

## Learning Resources

- [Official ROS2 Documentation](https://docs.ros.org/en/jazzy/)
- [ROS2 Tutorials](https://docs.ros.org/en/jazzy/Tutorials.html)
- [ROS2 Design](https://design.ros2.org/)

## Common Commands

**List all nodes:**
```bash
ros2 node list
```

**List all topics:**
```bash
ros2 topic list
```

**Inspect a topic:**
```bash
ros2 topic info /topic_name
ros2 topic echo /topic_name
```

**List services:**
```bash
ros2 service list
```

**Call a service:**
```bash
ros2 service call /service_name service_type_name '{args}'
```

**List actions:**
```bash
ros2 action list
```

**Send an action goal:**
```bash
ros2 action send_goal /action_name action_type_name '{goal: value}'
```

**View node parameters:**
```bash
ros2 param list /node_name
ros2 param get /node_name param_name
```

**Set parameter:**
```bash
ros2 param set /node_name param_name value
```

## ROS2 CLI Tools

Essential tools for development:
```bash
ros2 node info /node_name           # Node details
ros2 topic pub /topic_name msg_type '{data: value}'  # Publish manually
ros2 bag record -a                  # Record all topics
ros2 bag play rosbag2_*             # Playback recording
ros2 doctor                         # System health check
ros2 launch package_name launch_file.py  # Run launch files
ros2 test package_name              # Run package tests
```

## Troubleshooting

### Node not found
Ensure workspace is sourced:
```bash
source install/setup.bash
ros2 node list
```

### Topic not publishing
Check node is running:
```bash
ros2 node info /node_name
ros2 topic info /topic_name
```

### Build issues
Clean and rebuild:
```bash
rm -rf build install log
colcon build
```

## Next Steps

- Apply concepts to mars_rover_ws*
- Create custom ROS2 packages
- Explore advanced features: lifecycle, composition, middleware

---

**Last Updated**: 2026-03-16  
**Maintainer**: p0531d0n
