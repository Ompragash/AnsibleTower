# Login to Tower Node and follow the below commands:

## 1. Unregister the isolated rabbitmq queue:

`# awx-manage unregister_queue --queuename="isolated_instance_name"`

## 2. Unregister the isoalted node:

`# awx-manage deprovision_instance --hostname="isolated.tower.com"`

## 3. Register the isolated node again:

`# awx-manage register_instance --hostname="isolated.tower.com"`

## 4. Register the isolated rabbitmq queue again:

`# awx-manage register_queue --queuename="isolated_instance_name" --hostnames="isolated.tower.com" --controller="tower"`
