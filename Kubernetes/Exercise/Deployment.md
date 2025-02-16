Deployment - 1
Introduction: Let us start with Deployments! Given a deployment-definition.yml file. We are only getting started with it, so let's get it populated. 

Instruction: Add all the root level properties to it. Note: Only add the properties, not any values yet
```yaml
apiVersion:
kind:
metadata:
spec:
```


Deployment - 2
Introduction: Let us now add values for Deployment. Deployment is under apiVersion apps/v1 

Instruction: Update values for apiVersion and kind
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
spec:
```



Deployment - 3
Introduction: Let us now add values for metadata 

Instruction: Name the Deployment frontend. And add labels app=>mywebsite and tier=> frontend
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
```


Deployment - 4
Introduction: Let us now get to the specification 

Instruction: The spec section for Deployment has 3 fields: replicas, template and selector. Simply add these properties. Do not add any values.
```yaml
apiVersion: apps/v1
kind: Deployment
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


Deployment - 5
Instruction: Let us update the number of replicas to 4.
```yaml
apiVersion: apps/v1
kind: Deployment
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


Deployment - 6
Introduction: The template section expects a Pod definition. Luckily, we have the one we created in the previous set of exercises. Next to the deployment-definition.yml you will now find the same pod-definition.yml file that you created before. 

Instruction: Let us now copy the contents of the pod-definition.yml file, except for the apiVersion and kind and place it under the template section. Take extra care on moving the contents to the right so it falls under template

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
  containers:
    - name: nginx
      image: nginx
```
```yaml
apiVersion: apps/v1
kind: Deployment
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


Deployment - 7
Introduction: Let us now link the pods to the Deployment by updating selectors. 

Instruction: Add a property "matchLabels" under selector and copy the labels defined in the pod-definition under it. 

Note: this may not work in play-with-k8s as it runs on 1.8 version of kubernetes
```yaml
apiVersion: apps/v1
kind: Deployment
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

https://uklabs.kodekloud.com/topic/labs-deployments-2/

