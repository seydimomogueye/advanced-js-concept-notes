# Implementation of the Deployment Pipeline: Initial Stages

## Spinning Up the Continuous Deployment Virtual Machine

```shell
cd..
git clone https://github.com/vfarcic/ms-lifecycle.git 4
cd ms-lifecycle
vagrant up cd
vagrant ssh cd
```

## Deployment Pipeline Steps

1. Check out the code
2. Run pre-deployment tests
3. Compile and/or package the code
4. Build the container
5. Push the container to the registry
6. Deploy the container to the production server 7. Integrate the container
7. Run post-integration tests
8. Push the tests container to the registry
