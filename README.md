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


