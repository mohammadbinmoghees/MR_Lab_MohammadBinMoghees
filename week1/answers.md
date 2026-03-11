# Answers.md

## 1. Definitions

**Node:**
A node is an individual executable in ROS that performs a specific task, such as processing data, controlling hardware, or running an algorithm.

**Topic:**
A topic is a named communication channel used by ROS nodes to exchange messages asynchronously.

**Package:**
A package is the basic organizational unit in ROS that contains code, configuration files, dependencies, and resources for a specific functionality.

**Workspace:**
A workspace is a directory structure where ROS packages are developed, built, and organized together.

---

## 2. Why sourcing is required

Sourcing a workspace updates the environment variables so the system knows where to find the packages, executables, and dependencies inside that workspace.

If the workspace is not sourced, ROS will not recognize the packages you built, and commands like `ros2 run` will fail because the system cannot locate those nodes.

---

## 3. Purpose of `colcon build`

`colcon build` compiles and builds all packages in a ROS2 workspace.

After building, it generates the following folders:

* **build/** – contains intermediate compilation files.
* **install/** – contains the final installed packages and executables used when sourcing the workspace.
* **log/** – stores build logs and debugging information.

---

## 4. Purpose of `entry_points` console script in `setup.py`

The `entry_points` console script creates command-line executables that allow ROS2 to run Python nodes using `ros2 run`.

It maps a command name to a Python function (usually `main()`), so ROS2 knows which script to execute when the node is launched.

---

## 5. Publisher–Subscriber Topic Diagram

```
        publishes messages
   +--------------------+
   |    Publisher Node  |
   |   (e.g., sensor)   |
   +--------------------+
            |
            |   Topic: /data_topic
            v
      ----------------------
      |                    |
      |      /data_topic   |
      |                    |
      ----------------------
            |
            |   receives messages
            v
   +--------------------+
   |   Subscriber Node  |
   |  (e.g., processor) |
   +--------------------+
```

The publisher sends messages to the topic, and the subscriber listens to that topic and receives the messages.
