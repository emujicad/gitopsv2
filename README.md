# gitopsv2
gitopsv2 test


Notes:

Instalar flux em un gti provider que no sea gitlab o github. Ejemplo bitbucket

export USER=<user-name>   # foo-dev
export PASSWORD=<user-password>   # foo-dev
export CLUSTER=<k8s-cluster-name>   # foo-dev
flux bootstrap git --url=https://bitbucket.org/project/gitops-repo.git --branch=master --username=$USER --password=$PASSWORD --path=clusters/$CLUSTER


#Con GITLAB 

export GITLAB_TOKEN=<gitlab-token>
export CLUSTER=<k8s-cluster-name>   # foo-dev
export GITLAB_REPO=<gitlab-repo-name> gitops-foo-dev
export GITLAB_OWNER="foo/xxx/yyyy"

flux bootstrap gitlab --ssh-hostname=gitlab.com --owner=$GITLAB_OWNER --repository=$GITLAB_REPO --branch=main --token-auth --path=clusters/$CLUSTER


Create a sealed secret


kubectl create secret -n default generic my-secret --from-literal='ADMIN_USER=admin' --from-literal='ADMIN_PWD=Password' --dry-run=client -o json | kubeseal -o yaml > my-secret.sealed.yaml

kubectl create secret -n default generic my-secret --from-literal='ADMIN_USER=admin' --from-literal='ADMIN_PWD=Password' --dry-run=client -o yaml | kubeseal -o yaml > my-secret.sealed.yaml


