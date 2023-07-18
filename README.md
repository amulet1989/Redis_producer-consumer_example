# Redis Producer/Consumer example

You can see this code example to understand how to use Redis message queue and hash table to communicate two services.

For this particular case, the Producer and Consumer services are two Jupyter notebooks you must launch and run. Please check the next image of the system architecture.

**Figure 1. System_architecture**
![System_architecture](https://i.imgur.com/IzKD0b8.png)

## Install and run

1. You must install some Python packages to run this example, with `pip` already installed on your computer. You could create a virtual environment and then install requirements.  
Please run:

```bash
$ pip install -r requirements.txt
```

2. Then, you need to launch a Redis service, for this, we will use a Docker container. If you didn't know Docker in detail no worries, just make sure the following command runs without errors and you will be fine:

```bash
$ docker-compose up
```

You should see something like this:

```
[+] Running 2/2
 ⠿ Network 1442-theory-redis_default    Created                                                                                                                                                                0.0s
 ⠿ Container 1442-theory-redis-redis-1  Created                                                                                                                                                                0.0s
Attaching to 1442-theory-redis-redis-1
1442-theory-redis-redis-1  | 1:C 11 Aug 2022 21:42:46.449 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1442-theory-redis-redis-1  | 1:C 11 Aug 2022 21:42:46.449 # Redis version=6.2.6, bits=64, commit=00000000, modified=0, pid=1, just started
1442-theory-redis-redis-1  | 1:C 11 Aug 2022 21:42:46.449 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
1442-theory-redis-redis-1  | 1:M 11 Aug 2022 21:42:46.449 * monotonic clock: POSIX clock_gettime
1442-theory-redis-redis-1  | 1:M 11 Aug 2022 21:42:46.450 * Running mode=standalone, port=6379.
1442-theory-redis-redis-1  | 1:M 11 Aug 2022 21:42:46.450 # Server initialized
1442-theory-redis-redis-1  | 1:M 11 Aug 2022 21:42:46.451 * Ready to accept connections
```

*Tip:* If you want to stop it, use `Ctrl+C` keys.

3. Finally, let's run Jupyter so we can open our notebooks:
   - [Redis_Producer.ipynb](https://github.com/amulet1989/Redis_producer-consumer_example/blob/main/Redis_Producer.ipynb) It's the user that asks for service, it adds tasks to the Redis queue and waits for the answer by reading the Hash Table.
   - [Redis_Consumer.ipynb](https://github.com/amulet1989/Redis_producer-consumer_example/blob/main/Redis_Consumer.ipynb) It's the service that is reading the queue for users' tasks and returns the answers for every task through a Hash table.

```bash
$ jupyter notebook
```

Now go to your browser and start playing with the Consumer/Producer notebooks.
