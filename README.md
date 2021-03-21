# K8S Training

This is a repo for my k8s training purposes and contains some couple of stuff that i made in order to discover and learn `Kubernetes`.

I use a local k8s cluster with `minikube`.

## Content

### demo-mongo

- Presentation

    The `demo-mongo` folder contains a simple example of `mongo-db` and `mongo-express` deployment setup for a basic `k8s cluster`. It contains two sub-folders that respectively named `mongo-db` and `mongo-express` and each of those also contains necessary `yaml` configuration files that allow you to properly run an instance of a `mongo-express` application that communicate with a `mongo` database.
    In order to have a better organization, i also created a namespace which its configuration is in `demo-mongo-ns.yaml` file and with that, all components of this simple setup gonna be available there.

- Setup

    - First, create the namespace with the following command after being placed in the `demo-mongo` folder : `kubctl apply -f demo-mongo-ns.yaml`

    - Execute the following command in order to have the `mongo-db` instance setup :
        - `kubectl apply -f mongo-db/secret.yaml` 
        - `kubectl apply -f mongo-db/service.yaml` 
        - `kubectl apply -f mongo-db/deployment.yaml`

    - Execute the following command in order to have the `mongo-express` instance setup :
        - `kubectl apply -f mongo-express/secret.yaml` 
        - `kubectl apply -f mongo-express/configmap.yaml` 
        - `kubectl apply -f mongo-express/service.yaml` 
        - `kubectl apply -f mongo-express/deployment.yaml`

    - Execute the following command in order to launch `mongo-express` app in your default browser (i use `minikube` here) :
        - `minikube service mongo-express-svc -n demo-mongo` 

    - The credentials for accessing `mongo-express` web app are `mongo-express-username` as username and `mongo-express-password` for the password.

## Contributing

Feel free to make a PR or report an issue 😃

Oh, one more thing, please do not forget to put a description when you make your PR 🙂

## Author

- [M.B.C.M](https://itdev.sn)
[![My Twitter Link](https://img.shields.io/twitter/follow/the_it_dev?style=social)](https://twitter.com/the_it_dev)