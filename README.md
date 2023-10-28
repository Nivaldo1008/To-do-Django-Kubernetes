# kubernetes-django-app
To-do using Django + Kubernetes

## Deployment

 - Build app image `docker build -t kubernetes-django .`
 - Create deployment `kubectl apply -f deployment.yml`
 - Expose service `kubectl expose deploy kubernetes-django-deployment --type=NodePort`
 - Get mapped port for the app `kubectl get service`
 - Visit `http://localhost:<PORT>` in the browser.


## Deployment of new versions of the application
 - Make changes in to the app
 - `docker build -t kubernetes-django:v2 .`
 - Update image at the `deployment.yml` file `spec.template.spec.containers.image` to the `kubernetes-django:v2`
 - `kubectl apply -f deployment.yml`
 - App should be updated to the new version now.
