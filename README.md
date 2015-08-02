# docker-openfalcon-task

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-task .
```

## Run

### Basic Run

Use default mysql account, configuration, and falcon-task package.

```
$sudo docker run -dti --name task -p 8001:8001 openfalcon-task
```

### Advanced Run

+ Self-defined mysql accoun and configuration

    Replace file **cfg.json** in the volume */config*.  
    For more detail about **cfg.json**, see [Task](http://book.open-falcon.com/zh/install/task.html).

+ New falcon-task package

    Replace file **falcon-task.tar.gz** in the volume */package*.
    
For example, **cfg.json** in /tmp/config and **falcon-task.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name task -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 8001:8001 openfalcon-task
```
