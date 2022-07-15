<h1 align="center">
  <img alt="logo" src="https://adinermie.com/wp-content/uploads/2019/08/HashiVault.png" width="224px"/><br/>
  Vault Labs
</h1>
<p align="center">Quickly bootstrap and create vault implementations, for fun, <b>certification preparations</b> (very handy), <b>break things safely :)</b> or whatever you like.<br/><br/>Focus on <b>writing</b> code and <b>thinking</b> of business-logic! The CLI will take care of the rest.</p>

## ⚡️ Quick start

First, ensure you have [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/install/) installed. Ah, yes.. also [TaskFile](taskfile.dev/).

Then, run the following command:

```bash
# Bootstrap the lab (every "implementation type is called lab" vault with consul
task vault-lab-consul-simple
```
Then, drink coffee ☕️ and wait until [Docker Compose](https://docs.docker.com/compose/overview/) finishes.


## ⚙️ Lab

Labs are meant to gather all use-cases and different "flavors" of the recommended vault reference architecture.
(This list will increase as we add more implementations.)

| Lab                                 | Description                                                                      | status | Enable                     | location                                        |
|-------------------------------------|----------------------------------------------------------------------------------|--------|----------------------------|-------------------------------------------------|
| `Vault with consul storage backend` | Enables Vault, with Consul as its storage backend. It includes one Consul worker | ✅      | `vault-lab-consul-simple ` | [source](ref-architectures/vault-consul-simple) |


## ⭐️ Project assistance
- Oh, please do. Any new lab will be more than welcome!

Together, we can make this project **better** every day! 😘
