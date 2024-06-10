on each node:
- need to create user and group with UID/GID 1000
- sudo useradd -u 1000 cockroach
- sudo groupadd -g 1000 cockroach
- sudo groupmod -g 1000 cockroach
- then change the ownership of /cockroachdb-data
- sudo chown -R 1000:1000 /cockroachdb-data

- kubectl apply -f https://raw.githubusercontent.com/rancher/local-path-provisioner/master/deploy/local-path-storage.yaml

- kubectl exec -it cockroachdb-client-secure -- ./cockroach sql --certs-dir=./cockroach-certs --host=crdb-release-cockroachdb-public
- CREATE USER qaz WITH PASSWORD 'qaz123';
- GRANT admin TO qaz;
