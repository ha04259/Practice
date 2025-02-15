
Pods - 1
Introduction: Let us start simple! Given a pod-definition.yml file. We are only getting started with it. I have added two root level properties - apiVersion and kind.
Instruction: Add the missing two properties - metadata and spec
Here's the YAML structure in a code block with proper indentation:

```yaml
apiVersion:  # e.g., v1, apps/v1 (Kubernetes API version)
kind:        # e.g., Pod, Deployment, Service (resource type)
metadata:
  name:      # Resource name
  labels:    # Key-value pairs
    key: value
spec:        # Desired state of the resource
  # Configuration details specific to the resource type
```

Pods - 2
Introduction: Let us now populate values for each property. Start with apiVersion. 

Instruction: Update value of apiVersion to v1. Remember to add a space between colon (:) and the value (v1)

```yaml
apiVersion: v1
kind:
metadata:
spec:
```

Pods - 3
Instruction: Update value of kind to Pod.
```yaml
apiVersion: v1
kind: Pod
metadata:
spec:
```

Pods - 4
Introduction: Let us now get to the metadata section. 

Instruction: Add a property "name" under metadata with value "myapp-pod". Remember to add a space before 'name' to make it a child of metadata
```yaml
apiVersion: v1
kind: Pod
metadata:
    name: myapp-pod
spec:
```

Pods - 5
Introduction: Let us add some labels to our Pod 

Instruction: Add a property "labels" under metadata with a child property "app" with a value "myapp". Remember to have equal number of spaces before "name" and "labels" so they are siblings
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels: 
    app: myapp
spec:
```

Pods - 6
Introduction: We now need to provide information regarding the docker image we plan to use. 

Instruction: Add a property containers under spec section. Do not add anything under it yet.
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
  containers:
```

Pods - 7
Instruction: Containers is an array/list. So create the first element/item in the array/list and add the following properties to it: name - nginx and image - nginx
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
Pods - 8
Introduction: Perfect! You have successfully created a Kubernetes-Definition file. Let us try it one more time, this time all on your own! 

Instruction: Create a Kubernetes Pod definition file using values below: 

* Name: postgres 
* Labels: tier => db-tier
* Container name: postgres
* Image: postgres
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
```

Pods - 9
Introduction: Postgres Docker image requires an environment variable to be set for password.  

Instruction: Set an environment variable for the docker container. POSTGRES_PASSWORD with a value mysecretpassword. I know we haven't discussed this in the lecture, but it is easy. To pass in an environment variable add a new property 'env' to the container object. It is a sibling of image and name. env is an array/list. So add a new item under it. The item will have properties name and value. name should be the name of the environment variable - POSTGRES_PASSWORD. And value should be the password - mysecretpassword
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
      env:
        - name: POSTGRES_PASSWORD
          value: mysecretpassword
```
