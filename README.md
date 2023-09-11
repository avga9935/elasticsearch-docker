docker build -t my-es-image .

docker volume create --name esdata

docker run --rm -ti -p 9200:9200 -v esdata:/usr/share/elasticsearch/data --memory="4g" -e ES_HEAP_SIZE=2g my-es-image



expected output -

```
WARNING: Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
[2023-09-11 17:51:46,933][INFO ][node                     ] [Janet van Dyne] version[2.4.6], pid[1], build[5376dca/2017-07-18T12:17:44Z]
[2023-09-11 17:51:46,933][INFO ][node                     ] [Janet van Dyne] initializing ...
[2023-09-11 17:51:47,400][INFO ][plugins                  ] [Janet van Dyne] modules [reindex, lang-expression, lang-groovy], plugins [], sites []
[2023-09-11 17:51:47,429][INFO ][env                      ] [Janet van Dyne] using [1] data paths, mounts [[/usr/share/elasticsearch/data (/dev/sda1)]], net usable_space [29.4gb], net total_space [39gb], spins? [possibly], types [ext4]
[2023-09-11 17:51:47,430][INFO ][env                      ] [Janet van Dyne] heap size [1.9gb], compressed ordinary object pointers [true]
[2023-09-11 17:51:49,230][INFO ][node                     ] [Janet van Dyne] initialized
[2023-09-11 17:51:49,231][INFO ][node                     ] [Janet van Dyne] starting ...
[2023-09-11 17:51:49,357][INFO ][transport                ] [Janet van Dyne] publish_address {172.17.0.2:9300}, bound_addresses {0.0.0.0:9300}
[2023-09-11 17:51:49,365][INFO ][discovery                ] [Janet van Dyne] docker-cluster/0SKX-5yMRZO4JSDp4rr6sQ
[2023-09-11 17:51:52,459][INFO ][cluster.service          ] [Janet van Dyne] new_master {Janet van Dyne}{0SKX-5yMRZO4JSDp4rr6sQ}{172.17.0.2}{172.17.0.2:9300}, reason: zen-disco-join(elected_as_master, [0] joins received)
[2023-09-11 17:51:52,519][INFO ][http                     ] [Janet van Dyne] publish_address {172.17.0.2:9200}, bound_addresses {0.0.0.0:9200}
[2023-09-11 17:51:52,519][INFO ][node                     ] [Janet van Dyne] started
[2023-09-11 17:51:52,529][INFO ][gateway                  ] [Janet van Dyne] recovered [0] indices into cluster_state
```
