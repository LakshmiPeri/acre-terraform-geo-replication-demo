[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]


[![Terraform CI](https://github.com/redisgeek/acre-terraform-geo-replication-simple/actions/workflows/terraform-ci.yml/badge.svg)](https://github.com/redisgeek/acre-terraform-geo-replication-simple/actions/workflows/terraform-ci.yml)

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fredisgeek%2Facre-terraform-geo-replication-simple%2Fmain%2FARM%2FACRE%2Fcluster.json)

# acre-terraform-geo-replication-simple
## Deploy Azure Cache for Redis Enterprise (ACRE) in two separate regions with active geo-replication

Use the latest "azurerm" Terraform provider,
combined with the latest ARM templates, to deploy
Azure Cache for Redis Enterprise (ACRE)
in two separate regions with active geo-replication

- _Tenant_
    - _Subscription_
        - **Resource Group**
            - **Redis Enterprise Cluster in Region 1**
            - **Redis Enterprise Cluster in Region 2**

### Built with:

* [Terraform](https://terraform.io)

## | [Getting Started](#getting-started) | [See Also](#see-also)  | [License](#license) |

## Secrets

- AZURE_SUBSCRIPTION_ID
- AZURE_TENANT_ID
- AZURE_CLIENT_SECRET
- AZURE_CLIENT_ID

## Getting Started

```bash
  git clone https://github.com/redisgeek/acre-terraform-geo-replication-simple
  cd acre-terraform-geo-replication-simple
  terraform init
```
The output should include:
```text
  Terraform has been successfully initialized!
```
Copy the variables template.
```bash
cp terraform.tfvars.example terraform.tfvars
```
>Update terraform.tfvars with your [secrets](#secrets)
and set the regions you want to deploy to.

```bash
vi terraform.tfvars
```

```bash
terraform plan
terraform apply
```

Have fun!

### Regions

There are default regions configured in the **variables.tf** file.
The ARM templates are expecting 3 AZs in the primary and none in the secondary.

### Cleanup

Remove the resources that were created.

```bash
terraform destroy
```

## See Also

[acre-terraform-geo-replication](https://github.com/redisgeek/acre-terraform-geo-replication)

## Roadmap

See the [open issues](https://github.com/redisgeek/acre-terraform-geo-replication-simple/issues) for a list of proposed features (and known issues).

## Contributing

Pull-requests are welcomed!

## License

Distributed under the MIT License. See `LICENSE` for more information.

[contributors-shield]: https://img.shields.io/github/contributors/redisgeek/acre-terraform-geo-replication-simple.svg?style=for-the-badge
[contributors-url]: https://github.com/redisgeek/acre-terraform-geo-replication-simple/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/redisgeek/acre-terraform-geo-replication-simple.svg?style=for-the-badge
[forks-url]: https://github.com/redisgeek/acre-terraform-geo-replication-simple/network/members
[stars-shield]: https://img.shields.io/github/stars/redisgeek/acre-terraform-geo-replication-simple.svg?style=for-the-badge
[stars-url]: https://github.com/redisgeek/acre-terraform-geo-replication-simple/stargazers
[issues-shield]: https://img.shields.io/github/issues/redisgeek/acre-terraform-geo-replication-simple.svg?style=for-the-badge
[issues-url]: https://github.com/redisgeek/acre-terraform-geo-replication-simple/issues
[license-shield]: https://img.shields.io/github/license/redisgeek/acre-terraform-geo-replication-simple.svg?style=for-the-badge
[license-url]: https://github.com/redisgeek/acre-terraform-geo-replication-simple/blob/master/LICENSE.txt