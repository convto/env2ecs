# env2ecs
environment variable to json ecs-task-definition's environment format.

# Example
Use this sample env.
```
ENV_A=a
ENV_B=b
ENV_C=c
```

Pass `env` command output to env2ecs, env2ecs converts to ecs-task-definition's environment format.

```
$ env | env2ecs
[{"name":"ENV_A","value":"a"},{"name":"ENV_B","value":"b"},{"name":"ENV_C","value":"c"}]
```

If you want format json, you can work with jq.

```
$ env | env2ecs | jq
[
  {
    "name": "ENV_A",
    "value": "a"
  },
  {
    "name": "ENV_B",
    "value": "b"
  },
  {
    "name": "ENV_C",
    "value": "c"
  }
]
```

# Installation
Please follow.
```
$ curl -L https://raw.githubusercontent.com/convto/etj/master/env2ecs > /usr/local/bin/env2ecs
$ chmod +x /usr/local/bin/env2ecs
```

# Usage
Pass env.
```
$ cat .env.test | env2ecs
```
