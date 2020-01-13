### Node.js component with hot-reload

Node.js example demonstrating the file synchronization mode.

#### Init

Deploy component from stack template once to render templates with SuperHub stack parameters:

```bash
make deploy COMPONENT=skaffold-nodejs
```

Alternativelly, edit `skaffold.yaml` and `templates/deployment.yaml` to set Docker image, and `templates/ingress.yaml` to set ingress hostname.
Then:

```bash
skaffold dev --kube-context $DOMAIN_NAME [--namespace default] [--default-repo <myrepo>] [--port-forward] [--cleanup=false]
```

https://skaffold.dev/docs/environment/kube-context/

https://skaffold.dev/docs/environment/image-registries/

#### Workflow

* Make some changes to `index.js`:
    * The file will be synchronized to the cluster
    * `nodemon` will restart the application
* Make some changes to `package.json`:
    * The full build/push/deploy process will be triggered, fetching dependencies from `npm`
