ReplicaSet - 1
Introduction: Let us start with ReplicaSets! Given a blank replicaset-definition.yml file. We are only getting started with it, so let's get it populated. 

Instruction: Add all the root level properties to it. 

Note: Only add the properties, not any values yet.
```yaml
apiVersion:
kind:
metadata:
spec:
```


ReplicaSet - 2
Introduction: Let us now add values for ReplicaSet. ReplicaSet is under apiVersion - apps/v1 

Instruction: Update values for apiVersion and kind
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
spec:
```


ReplicaSet - 3
Introduction: Let us now add values for metadata 

Instruction: Name the ReplicaSet - frontend. And add labels app=>mywebsite and tier=> frontend
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
```


ReplicaSet - 4
Introduction: Let us now get to the specification 

Instruction: The spec section for ReplicaSet has 3 fields: replicas, template and selector. Simply add these properties. Do not add any values yet.
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas:
  template:
  selector:
```



ReplicaSet - 5
Instruction: Let us update the number of replicas to 4.
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
  selector:
```


ReplicaSet - 6
Introduction: The template section expects a Pod definition. Luckily, we have the one we created in the previous set of exercises. Next to the replicaset-definition.yml you will now find the same pod-definition.yml file that you created before. 

Instruction: Let us now copy the contents of the pod-definition.yml file, except for the apiVersion and kind and place it under the template section. Take extra care on moving the contents to the right so it falls under template.
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
  selector:
```


ReplicaSet - 7
Introduction: Let us now link the pods to the ReplicaSet by updating selectors. 

Instruction: Add a property "matchLabels" under selector and copy the labels defined in the pod-definition under it. 

Note: This may not work in play-with-k8s as it runs on 1.8 version of kubernetes. ReplicaSets moved to apps/v1 in 1.9 version of Kubernetes.
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
  selector:
   matchLabels:
     app: myapp
```

https://uklabs.kodekloud.com/topic/labs-replica-sets-2/

