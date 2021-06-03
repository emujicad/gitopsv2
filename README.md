# gitopsv2
gitopsv2 test


Notes:

Create a sealed secret


kubectl create secret -n default generic my-secret --from-literal='ADMIN_USER=admin' --from-literal='ADMIN_PWD=Password' --dry-run=client -o json | kubeseal -o yaml > my-secret.sealed.yaml

kubectl create secret -n default generic my-secret --from-literal='ADMIN_USER=admin' --from-literal='ADMIN_PWD=Password' --dry-run=client -o yaml | kubeseal -o yaml > my-secret.sealed.yaml