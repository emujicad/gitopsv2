# gitopsv2
gitopsv2 test


Notes:

Instalar flux em un gti provider que no sea gitlab o github. Ejemplo bitbucket


flux bootstrap git --url=https://bitbucket.org/project/gitops-repo.git --branch=master --username=USER --password=PASSWORD --path=clusters/CLUSTER


Create a sealed secret


kubectl create secret -n default generic my-secret --from-literal='ADMIN_USER=admin' --from-literal='ADMIN_PWD=Password' --dry-run=client -o json | kubeseal -o yaml > my-secret.sealed.yaml

kubectl create secret -n default generic my-secret --from-literal='ADMIN_USER=admin' --from-literal='ADMIN_PWD=Password' --dry-run=client -o yaml | kubeseal -o yaml > my-secret.sealed.yaml