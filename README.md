### launch_tests_pkg

#### Notes

##### 1. Parameters vs arguments

This node definition has both:
```
    rviz_node = Node(
        package='rviz2',
        executable='rviz2',
        output='screen',
        name='rviz_node',
        parameters=[{'use_sim_time': True}],
        arguments=['-d', rviz_config_dir])
```  
`use_sim_time` is a parameter that every node has and is automatically generated.  
`-d` is the argument for the directory to the rviz2 config file. This is provided on the command line.    

##### 2. `launch` vs `run`

1. `launch` requires a launch file (Python, XML, or YAML) which is usually under `/launch` directory
```
ros2 launch <pkg_name> <launch_file_name> arg1=:some_value1 arg2=:some_value2
```
or
```
ros2 launch <path_to_launch_file> arg1=:some_value1 arg2=:some_value2
```

2. `run` requires an executable which is usually under a `/lib` directory
```
ros2 run <pkg_name> <executable_name> --ros-args arg1=:some_value1 arg2=:some_value2
```

#### 3 versions of launch

| Language | Main | Rviz2 | Move robot | Exe source |
| --- | --- | --- | --- | --- |
| Python | [python_main.launch.py](launch/python_main.launch.py) | [start_rviz_with_arguments.launcy.py](launch/start_rviz_with_arguments.launcy.py) | [move_with_arguments.launch.py](launch/move_with_arguments.launch.py) | [move_robot_with_arguments.cpp](src/move_robot_with_arguments.cpp) |
| XML | [xml_main.launch.py](launch/xml_main.launch.py) | [start_rviz_with_arguments.launcy.py](launch/start_rviz_with_arguments.launcy.py) | [move_with_arguments.launch.xml](launch/move_with_arguments.launch.xml) | [move_robot_with_params.cpp](src/move_robot_with_params.cpp) |
