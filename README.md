# RabitMQ-python

- To install the pika client

```
python -m pip install pika --upgrade
```

- Install the rabbitMq client using the docker image:
  
```
docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.11-management
```

- The repo consits of  well written small programs in Python.
- A producer (sender) that sends a single message, and a consumer (receiver) that receives messages and prints them out.
- It's a "Hello World" of messaging.
- Our first program `send.py` will send a single message to the queue.
- Our second program `receive.py` will receive messages from the queue and print them on the screen.
- Out third program `new_task.py` will schedule tasks to our work queue.
- Our fourth program `worker.py` needs to fake a second of work for every dot in the message body. It will pop messages from the queue and perform the task.
- Our fifth program `emit_logs.py` establishes the connection we declared for the exchange. This step is necessary as publishing to a non-existing exchange is forbidden.
- Our sixth program `receiver_logs.py` will recieve all the logs.
- Our seventh program `emit_log_direct.py` we improved our logging system. Instead of using a fanout exchange only capable of dummy broadcasting, we used a direct one, and gained a possibility of selectively receiving the logs.
- Our eigth program `receiver_log_direct.py` will recieve all the logs.
- Our ninth program `emit_log_topic.py`  we may want to listen to just critical errors coming from 'cron' but also all logs from 'kern'.
- Our tenth program `receive_logs_topic.py` we will recieve only crtical logs.
