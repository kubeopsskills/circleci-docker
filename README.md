# KubeOps CircleCI Docker

**KubeOps CircleCI Docker** is a collection of container images which we're using in our CI/CD pipelines in wide ranges of customers.

This is a project built with ❤️ by [KubeOps Skills](https://www.kubeops.guru). We encourage you to try it out, [leave feedback](#help--feedback), and [jump in to help](#contributing)!

### Contents
- [Versioning](#versioning)
- [Help & Feedback](#help--feedback)
- [Contributing](#contributing)
- [License](#license)

## Versioning
| Container Image with Tag | Description | Feature |
|----------------|------------ |---------------------|
| public.ecr.aws/kubeopsskills/circleci:1.0.2-docker-aws | Docker in Docker with AWS support | Docker, Git, AWS CLI |
| public.ecr.aws/kubeopsskills/circleci:1.0.1-kubernetes-kustomize-aws | kubectl & kustomize with AWS support  | kubectl, kustomize, AWS CLI |
| public.ecr.aws/kubeopsskills/circleci:1.0.0-docker-azure | Docker in Docker with Azure support | Docker, Git, Azure CLI |
| public.ecr.aws/kubeopsskills/circleci:1.0.0-kubernetes-kustomize-azure | kubectl & kustomize with Azure support | kubectl, kustomize, Azure CLI |

## Help & Feedback
Interacting with the community and the development team is a great way to
contribute to the project. Please consider the following venues (in order):

* Search [open issues](https://github.com/kubeopsskills/circleci-docker/issues)

## Contributing

We welcome community contributions and pull requests. See our [contribution
guide](./CONTRIBUTING.md) for more information on how to report issues, set up a
development environment and submit code.

## License

This project is distributed under the [MIT License, Copyright (c) 2020 KUBEOPS SKILLS Co., Ltd.](./LICENSE)