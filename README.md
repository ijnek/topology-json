# topology-json

Json files to use when benchmarking ROS2 communication with [ros2-performance](https://github.com/irobot-ros/ros2-performance/tree/master/performances#ros2-performance-framework)

## Running

Follow [instructions from ros2-performance](https://github.com/irobot-ros/ros2-performance/tree/master/performances#ros2-performance-framework), but instead of running
```
./irobot-benchmark topology/sierra_nevada.json
```
run
```
./irobot-benchmark <absolute-path-of-simple_architecture.json>
```

## Expected output
```
[INFO] [1631271602.126029242] [node_1]: Node node_1 created with executor id 0
[INFO] [1631271602.146551267] [node_1]: Publisher to topic_1 created
[INFO] [1631271602.148498833] [node_1]: Publisher to topic_2 created
[INFO] [1631271602.159300121] [node_2]: Node node_2 created with executor id 0
[INFO] [1631271602.162558631] [node_2]: Subscriber to topic_1 created
[INFO] [1631271602.164164159] [node_2]: Server to service_2 created
[INFO] [1631271602.173403000] [node_3]: Node node_3 created with executor id 0
[INFO] [1631271602.175987155] [node_3]: Client to service_2 created
[INFO] [1631271602.188046964] [multi_node_1]: Node multi_node_1 created with executor id 0
[INFO] [1631271602.190592390] [multi_node_1]: Subscriber to topic_1 created
[INFO] [1631271602.202128216] [multi_node_2]: Node multi_node_2 created with executor id 0
[INFO] [1631271602.204057299] [multi_node_2]: Subscriber to topic_1 created
[INFO] [1631271602.215809605] [multi_node_3]: Node multi_node_3 created with executor id 0
[INFO] [1631271602.217360281] [multi_node_3]: Subscriber to topic_1 created
[INFO] [1631271602.230107987] [multi_node_4]: Node multi_node_4 created with executor id 0
[INFO] [1631271602.232002759] [multi_node_4]: Subscriber to topic_1 created
[INFO] [1631271602.243794145] [multi_node_5]: Node multi_node_5 created with executor id 0
[INFO] [1631271602.245740364] [multi_node_5]: Subscriber to topic_1 created
Subscriptions and clients stats:
node           topic          size[b]   received[#]    late[#]   too_late[#]    lost[#]   mean[us]  sd[us]    min[us]   max[us]   freq[hz]  duration[s]
node_2         topic_1        10        498            9         1              0         469       724       98        9224      100       5         
node_3         service_2      0         496            61        5              0         1435      1097      376       9995      100       5         
multi_node_1   topic_1        10        498            11        2              0         554       719       128       8410      100       5         
multi_node_2   topic_1        10        498            11        3              0         588       744       139       8494      100       5         
multi_node_3   topic_1        10        498            8         2              0         516       664       117       8316      100       5         
multi_node_4   topic_1        10        498            12        3              0         623       774       149       8576      100       5         
multi_node_5   topic_1        10        498            13        4              0         643       761       160       8656      100       5         

Publishers stats:
node           topic          size[b]   received[#]    late[#]   too_late[#]    lost[#]   mean[us]  sd[us]    min[us]   max[us]   freq[hz]  duration[s]
node_1         topic_1        10        0              0         0              0         188       154       61        2645      100       5         
node_1         topic_2        4194304   0              0         0              0         283       320       94        922       1         5         

System total:
received[#]    mean[us]  late[#]   late[%]   too_late[#]    too_late[%]    lost[#]   lost[%]   
3484           689       125       3.588     20             0.5741         0         0         
```
