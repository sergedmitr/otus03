# otus03
1. Create namespace zipper:

kubectl apply -f kube_manifest/.

kubectl config set-context --current --namespace zipper

2. Install PostgreSQL в minicube:

helm install postgresql-test oci://registry-1.docker.io/bitnamicharts/postgresql --set auth.database=mydb,auth.postgresPassword=secretpassword

3. Create secret(password) for DB:

kubectl create secret generic db-password --from-literal=password='secretpassword'

4. Run application with Helm:

helm install wsdb-local myapp/.

5. Run Postman collection:

newman run Otus03.json --verbose
