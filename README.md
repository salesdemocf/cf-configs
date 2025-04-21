Set the following variables before running command

``` shell
export ABBR=<Your Short Abbreviation, no longer than 4 characters>
export ENVIRONMENT_ABBR=<Environment Short Name>
export REGISTRY=<Image Registry FQDN>
export REPOSITORY=<Image Repository>
```

Run the following command once per environment you'd like to configure after setting the Environment Variables.

``` shell
cp -r workshop-template/abbr/  environments/$ENVIRONMENT_ABBR/$ABBR && cd environments/$ENVIRONMENT_ABBR/$ABBR && find . -type f -name "*.yaml" -exec sed -i .bak -e "s/abbr/$ABBR/g ; s/repository/$REPOSITORY/g ; s/registry/$REGISTRY/g" {} +
```
