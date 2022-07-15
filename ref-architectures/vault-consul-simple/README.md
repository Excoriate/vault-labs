# Vault with Consul storage backend (simple)
## ⚡️ Run
(From the root directory), using [TaskFile](taskfile.dev/):
```bash
# Bootstrap the lab (every "implementation type is called lab" vault with consul
task vault-lab-consul-simple
```

The expected outcome is
```bash
+] Building 633.6s (19/21)
 => [vault-consul-simple_vault internal] load build definition from Dockerfile                                                         0.0s
 => => transferring dockerfile: 855B                                                                                                   0.0s
 => [vault-consul-simple_consul internal] load build definition from Dockerfile                                                        0.0s
 => => transferring dockerfile: 886B                                                                                                   0.0s
 => [vault-consul-simple_consul-worker internal] load build definition from Dockerfile                                                 0.0s
 => => transferring dockerfile: 886B                                                                                                   0.0s
 => [vault-consul-simple_vault internal] load .dockerignore                                                                            0.0s
 => => transferring context: 2B                                                                                                        0.0s
 => [vault-consul-simple_consul internal] load .dockerignore                                                                           0.0s
 => => transferring context: 2B                                                                                                        0.0s
 => [vault-consul-simple_consul-worker internal] load .dockerignore                                                                    0.0s
 => => transferring context: 2B                                                                                                        0.0s
 => [vault-consul-simple_vault internal] load metadata for docker.io/library/alpine:3.14                                               2.3s
 => [vault-consul-simple_vault internal] load build context                                                                            0.0s
 => => transferring context: 560B                                                                                                      0.0s
 => [vault-consul-simple_vault 1/5] FROM docker.io/library/alpine:3.14@sha256:06b5d462c92fc39303e6363c65e074559f8d6b1363250027ed505  631.2s
 => => resolve docker.io/library/alpine:3.14@sha256:06b5d462c92fc39303e6363c65e074559f8d6b1363250027ed5053557e3398c5                   0.0s
 => => sha256:7bb52b4c2182c42732e518f044adc1c38959d374311d23961a6273dd01bc4499 528B / 528B                                             0.0s
 => => sha256:ac73e934f31119e38da975b98988cbd346af74f94455e6d465b9ce6c975762e7 1.49kB / 1.49kB                                         0.0s
 => => sha256:455c02918c4592a9beeeae47df541266f3ea53ed573feb767e5e8ab8dcee146e 2.72MB / 2.72MB                                         3.6s
 => => sha256:06b5d462c92fc39303e6363c65e074559f8d6b1363250027ed5053557e3398c5 1.64kB / 1.64kB                                         0.0s
 => => extracting sha256:455c02918c4592a9beeeae47df541266f3ea53ed573feb767e5e8ab8dcee146e                                              0.1s
 => [vault-consul-simple_consul-worker internal] load build context                                                                    0.0s
 => => transferring context: 502B                                                                                                      0.0s
 => [vault-consul-simple_consul internal] load build context                                                                           0.0s
 => => transferring context: 502B                                                                                                      0.0s
 => [vault-consul-simple_consul-worker 2/5] RUN mkdir /consul                                                                          0.2s
 => [vault-consul-simple_vault 2/5] RUN mkdir /vault                                                                                   0.2s
 => [vault-consul-simple_vault 3/5] RUN apk --no-cache add       bash       ca-certificates       wget                                11.1s
 => [vault-consul-simple_consul-worker 3/5] RUN apk --no-cache add       bash       ca-certificates       wget                        11.4s
 => [vault-consul-simple_vault 4/5] RUN wget --quiet --output-document=/tmp/vault.zip https://releases.hashicorp.com/vault/1.8.2/va  615.8s
 => [vault-consul-simple_consul 4/5] RUN wget --quiet --output-document=/tmp/consul.zip https://releases.hashicorp.com/consul/1.10.2  82.0s
 => [vault-consul-simple_consul-worker 5/5] COPY config/consul-config.json /consul/config/config.json                                  0.0s
 => [vault-consul-simple_vault] exporting to image                                                                                     0.5s
 => => exporting layers                                                                                                                0.3s
 => => writing image sha256:732dc7d8dc00bf5089e1ff6213d97876838aa215114ca3e0300f8e3fd49facd4                                           0.0s
 => => naming to docker.io/library/vault-consul-simple_consul                                                                          0.0s
 => => naming to docker.io/library/vault-consul-simple_consul-worker                                                                   0.0s
 => => writing image sha256:ed5523c8df5d0a12a28f6eb43e0d994a8888b242fa660a0c2e9ca139bcb9bf24                                           0.0s
 => => naming to docker.io/library/vault-consul-simple_vault                                                                           0.0s
 => [vault-consul-simple_vault 5/5] COPY config/vault-config.json /vault/config/vault-config.json                                      0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
[+] Running 4/4
 ⠿ Network vault-consul-simple_default            Created                                                                              0.0s
 ⠿ Container vault-consul-simple-consul-1         Started                                                                              0.4s
 ⠿ Container vault-consul-simple-consul-worker-1  Started                                                                              0.7s
 ⠿ Container vault-consul-simple-vault-1          Started                                                                              0.7s
docker images
Found existing alias for "docker images". You should use: "dim"
REPOSITORY                          TAG       IMAGE ID       CREATED          SIZE
vault-consul-simple_vault           latest    ed5523c8df5d   5 minutes ago    189MB
vault-consul-simple_consul-worker   latest    732dc7d8dc00   14 minutes ago   115MB
vault-consul-simple_consul          latest    732dc7d8dc00   14 minutes ago   115MB
bridgecrew/checkov                  latest    e8a58731c546   19 hours ago     452MB
bridgecrew/checkov                  <none>    73e8fe534d44   4 days ago       307MB
loadimpact/k6                       latest    49eabe138720   6 days ago       32.1MB
docker ps -a
Found existing alias for "docker ps -a". You should use: "dpa"
CONTAINER ID   IMAGE                               COMMAND                  CREATED         STATUS         PORTS                                                  NAMES
72742e2f1831   vault-consul-simple_vault           "vault server -confi…"   5 minutes ago   Up 5 minutes   0.0.0.0:8200->8200/tcp                                 vault-consul-simple-vault-1
df4481a70068   vault-consul-simple_consul-worker   "consul agent -serve…"   5 minutes ago   Up 5 minutes   8300/tcp, 8400/tcp, 8500/tcp, 8600/tcp                 vault-consul-simple-consul-worker-1
6bfe50268c69   vault-consul-simple_consul          "consul agent -serve…"   5 minutes ago   Up 5 minutes   8300/tcp, 8400/tcp, 8600/tcp, 0.0.0.0:8500->8500/tcp   vault-consul-simple-consul-1
```
