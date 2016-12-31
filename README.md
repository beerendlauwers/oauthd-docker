# oauthd-docker

## Tested on

- Ubuntu 16.04

## Prerequisites

- `docker`
- `docker-compose`

## Getting it up and running

1. Clone the repo
2. Go to the directory where `docker-compose.yml` is
3. Type `docker-compose build`
4. Ensure there were no errors (open up a ticket here otherwise)
5. Type `docker-compose up`, which should present something like this:
```
Starting redis-oauthd
Recreating oauthd-oauthd
Attaching to redis-oauthd, oauthd-oauthd
redis-oauthd     | 1:C 31 Dec 07:54:55.065 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
redis-oauthd     |                 _._                                                  
redis-oauthd     |            _.-``__ ''-._                                             
redis-oauthd     |       _.-``    `.  `_.  ''-._           Redis 3.2.6 (00000000/0) 64 bit
redis-oauthd     |   .-`` .-```.  ```\/    _.,_ ''-._                                   
redis-oauthd     |  (    '      ,       .-`  | `,    )     Running in standalone mode
redis-oauthd     |  |`-._`-...-` __...-.``-._|'` _.-'|     Port: 6379
redis-oauthd     |  |    `-._   `._    /     _.-'    |     PID: 1
redis-oauthd     |   `-._    `-._  `-./  _.-'    _.-'                                   
redis-oauthd     |  |`-._`-._    `-.__.-'    _.-'_.-'|                                  
redis-oauthd     |  |    `-._`-._        _.-'_.-'    |           http://redis.io        
redis-oauthd     |   `-._    `-._`-.__.-'_.-'    _.-'                                   
redis-oauthd     |  |`-._`-._    `-.__.-'    _.-'_.-'|                                  
redis-oauthd     |  |    `-._`-._        _.-'_.-'    |                                  
redis-oauthd     |   `-._    `-._`-.__.-'_.-'    _.-'                                   
redis-oauthd     |       `-._    `-.__.-'    _.-'                                       
redis-oauthd     |           `-._        _.-'                                           
redis-oauthd     |               `-.__.-'                                               
redis-oauthd     | 
redis-oauthd     | 1:M 31 Dec 07:54:55.066 # WARNING: The TCP backlog setting of 511 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of 128.
redis-oauthd     | 1:M 31 Dec 07:54:55.066 # Server started, Redis version 3.2.6
redis-oauthd     | 1:M 31 Dec 07:54:55.066 # WARNING overcommit_memory is set to 0! Background save may fail under low memory condition. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
redis-oauthd     | 1:M 31 Dec 07:54:55.066 # WARNING you have Transparent Huge Pages (THP) support enabled in your kernel. This will create latency and memory usage issues with Redis. To fix this issue run the command 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' as root, and add it to your /etc/rc.local in order to retain the setting after a reboot. Redis must be restarted after THP is disabled.
redis-oauthd     | 1:M 31 Dec 07:54:55.066 * DB loaded from disk: 0.000 seconds
redis-oauthd     | 1:M 31 Dec 07:54:55.066 * The server is now ready to accept connections on port 6379
oauthd-oauthd    | oauthd start server
oauthd-oauthd    | oauthd listening at http://[::]:6284 for http://localhost:6284
oauthd-oauthd    | Server is ready (load time: 0.9s) Sat, 31 Dec 2016 07:54:56 GMT
```

Finally, go to `localhost:6284` to configure the service. **NOTE:** [I have a ticket open with the `oauthd` repository because the frontend isn't working.](https://github.com/oauth-io/oauthd/issues/196)

## Further configuration

- There are several defaults in the `config.js` file. See [oauthd configuration](https://github.com/oauth-io/oauthd/wiki/Configuration) for details.
