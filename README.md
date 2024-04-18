![diagrams logo](assets/img/diagrams-header-nonlogo.png)

# Diagrams for Open Telekom Cloud

[![license](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)
[![pypi version](https://badge.fury.io/py/diagrams-otc.svg)](https://badge.fury.io/py/diagrams-otc)
![python version](https://img.shields.io/badge/python-%3E%3D%203.6-blue?logo=python)
<!-- ![Run tests](https://github.com/akyriako/diagrams/workflows/Run%20tests/badge.svg?branch=master) -->
<!-- [![todos](https://badgen.net/https/api.tickgit.com/badgen/github.com/akyriako/diagrams?label=todos)](https://www.tickgit.com/browse?repo=github.com/akyriako/diagrams)
![contributors](https://img.shields.io/github/contributors/akyriako/diagrams) -->

**Diagram as Code**.

> [!IMPORTANT] 
> Due to the fact that the upstream project seems to be inactive and non-processing/non-responsive to new Issues or Pull Requests for more than 2 years,
> the artifacts supporting Open Telekom Cloud has been moved to their own package. 
> Nevertheless, the repository retains its downstream status and any change that might come in the future either in the other 
> providers artifacts or in the code itself, will be synced. 
> Unless nothing changes, the package name in PyPi is from now on `diagrams-otc`. 


Diagrams lets you draw the cloud system architecture **in Python code**. It was born for **prototyping** a new system architecture design without any design tools. You can also describe or visualize the existing system architecture as well. Diagrams currently supports main major providers including: `AWS`, `Azure`, `GCP`, `Kubernetes`, `Alibaba Cloud`, `Oracle Cloud` etc... It also supports `On-Premise` nodes, `SaaS` and major `Programming` frameworks and languages.

**Diagram as Code** also allows you to **track** the architecture diagram changes in any **version control** system.

> [!NOTE] 
> It does not control any actual cloud resources nor does it generate cloud formation or terraform code. It is just for drawing the cloud system 
> architecture diagrams.

## Providers

![Open Telekom Cloud](https://img.shields.io/badge/OpenTelekomCloud-%23e20074?labelColor=%23e20074&link=https%3A%2F%2Fwww.open-telekom-cloud.com%2Fen)

in addition supports all the providers included in the original upstream:

![aws provider](https://img.shields.io/badge/AWS-orange?logo=amazon-aws&color=ff9900)
![azure provider](https://img.shields.io/badge/Azure-orange?logo=microsoft-azure&color=0089d6)
![gcp provider](https://img.shields.io/badge/GCP-orange?logo=google-cloud&color=4285f4)
![ibm provider](https://img.shields.io/badge/IBM-orange?logo=ibm&color=052FAD)
![kubernetes provider](https://img.shields.io/badge/Kubernetes-orange?logo=kubernetes&color=326ce5)
![alibaba cloud provider](https://img.shields.io/badge/AlibabaCloud-orange?logo=alibaba-cloud&color=ff6a00)
![oracle cloud provider](https://img.shields.io/badge/OracleCloud-orange?logo=oracle&color=f80000)
![openstack provider](https://img.shields.io/badge/OpenStack-orange?logo=openstack&color=da1a32)
![firebase provider](https://img.shields.io/badge/Firebase-orange?logo=firebase&color=FFCA28)
![digital ocean provider](https://img.shields.io/badge/DigitalOcean-0080ff?logo=digitalocean&color=0080ff)
![elastic provider](https://img.shields.io/badge/Elastic-orange?logo=elastic&color=005571)
![outscale provider](https://img.shields.io/badge/OutScale-orange?color=5f87bf)
![on premise provider](https://img.shields.io/badge/OnPremise-orange?color=5f87bf)
![generic provider](https://img.shields.io/badge/Generic-orange?color=5f87bf)
![programming provider](https://img.shields.io/badge/Programming-orange?color=5f87bf)
![saas provider](https://img.shields.io/badge/SaaS-orange?color=5f87bf)
![c4 provider](https://img.shields.io/badge/C4-orange?color=5f87bf)

## Getting Started

It requires **Python 3.7** or higher, check your Python version first.

It uses [Graphviz](https://www.graphviz.org/) to render the diagram, so you need to [install Graphviz](https://graphviz.gitlab.io/download/) to use **diagrams**. After installing graphviz (or already have it), install the **diagrams**.

> [!TIP]
> You can quickly install Graphviz either via pip: `pip install graphviz` (recommended) or via brew: `brew install graphviz` 

Install the Diagrams for Open Telekom Cloud directly from Pypi choosing one of the following methods:

```shell
# using pip (pip3)
$ pip install diagrams-otc

# using pipenv
$ pipenv install diagrams-otc

# using poetry
$ poetry add diagrams-otc
```

and then you are ready to try your very first OTC diagram by executing the Python code below:

```python
from diagrams import Diagram
from diagrams.opentelekomcloud.computing import Ecs
from diagrams.opentelekomcloud.database import Rds
from diagrams.opentelekomcloud.network import Elb
from diagrams.opentelekomcloud.network import Eip

with Diagram("Server Group Example OTC", show=False, direction="TB"):
    Eip("Elastic IPv4") >> Elb("Load Balancer") >> [Ecs("ECS-Worker-1"),
                  Ecs("ECS-Worker-2"),
                  Ecs("ECS-Worker-3"),
                  Ecs("ECS-Worker-4"),
                  Ecs("ECS-Worker-5")] >> Rds("Backend Database")
```

save it in a python file, e.g. `diagram.py` and execute it with the following command:

```python
python diagram.py
```

which will generate an diagram in PNG format:

![Server Group Example in OTC](assets/img/otc-example.png)

> [!NOTE] 
> The rest of the documentation and examples refer to the original
> upstream site as is.

You can start with [quick start](https://diagrams.mingrammer.com/docs/getting-started/installation#quick-start). Check out [guides](https://diagrams.mingrammer.com/docs/guides/diagram) for more details, and you can find all available nodes list in [here](https://diagrams.mingrammer.com/docs/nodes/aws).

## Examples

| Event Processing                                             | Stateful Architecture                                        | Advanced Web Service                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![event processing](https://diagrams.mingrammer.com/img/event_processing_diagram.png) | ![stateful architecture](https://diagrams.mingrammer.com/img/stateful_architecture_diagram.png) | ![advanced web service with on-premise](https://diagrams.mingrammer.com/img/advanced_web_service_with_on-premise.png) |

You can find all the examples on the [examples](https://diagrams.mingrammer.com/docs/getting-started/examples) page.

## Contributing

To contribute to diagram, check out [contribution guidelines](CONTRIBUTING.md).

## Other languages

- If you are familiar with Go, you can use [go-diagrams](https://github.com/blushft/go-diagrams) as well.

## License

[MIT](LICENSE)
