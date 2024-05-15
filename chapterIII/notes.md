#### Chapter III

- Kubernetes concepts related to specifying and hosting application deployments

- Deploying a contanierized application to Kubernetes on a cloud platform

- Updating deployments with new version of the application container

- Running a version of kubernetes locally for testing and development


#### Objects

- Pods

	One or many containers
	It's the unit of compute that Kubernetes schedules onto nodes according to the resources you require.
	

- Deployments

	High-order object that manages the Pod lifecyle.


- Services

	Are how you expose an application running on a set of Pods as a network services.
	Services get their own internal IP address and DNS record.

#### Deployment- use case

Handling differents replica using the same file.


### Troubleshooting

kubectl port-forward deploy/$DEPLOYMENT_NAME $FROM_PORT:$TO_PORT

### Imperative tip

kubectl create deployment timeserver \
--image=docker.io/wdennis/timeserver:1

kubectl expose deployment timeserver --type=LoadBalancer --port=80

	
