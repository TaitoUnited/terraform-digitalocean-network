# DigitalOcean network

Example usage:

```
provider "digitalocean" {
  token        = var.do_token
}

module "network" {
  source       = "TaitoUnited/network/digitalocean"
  version      = "1.0.0"

  name         = "my-infrastructure"
  region       = "ams2"

  network              = yamldecode(file("${path.root}/../infra.yaml"))["network"]
}
```

Example YAML:

```
network:
  ipRange: 10.10.10.0/24
```

Combine with the following modules to get a complete infrastructure defined by YAML:

- [DNS](https://registry.terraform.io/modules/TaitoUnited/dns/digitalocean)
- [Network](https://registry.terraform.io/modules/TaitoUnited/network/digitalocean)
- [Compute](https://registry.terraform.io/modules/TaitoUnited/compute/digitalocean)
- [Kubernetes](https://registry.terraform.io/modules/TaitoUnited/kubernetes/digitalocean)
- [Databases](https://registry.terraform.io/modules/TaitoUnited/databases/digitalocean)
- [Storage](https://registry.terraform.io/modules/TaitoUnited/storage/digitalocean)
- [PostgreSQL privileges](https://registry.terraform.io/modules/TaitoUnited/privileges/postgresql)
- [MySQL privileges](https://registry.terraform.io/modules/TaitoUnited/privileges/mysql)

TIP: Similar modules are also available for AWS, Azure, and Google Cloud. All modules are used by [infrastructure templates](https://taitounited.github.io/taito-cli/templates#infrastructure-templates) of [Taito CLI](https://taitounited.github.io/taito-cli/). See also [DigitalOcean project resources](https://registry.terraform.io/modules/TaitoUnited/project-resources/digitalocean), [Full Stack Helm Chart](https://github.com/TaitoUnited/taito-charts/blob/master/full-stack), and [full-stack-template](https://github.com/TaitoUnited/full-stack-template).

Contributions are welcome!
