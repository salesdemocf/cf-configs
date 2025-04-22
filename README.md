1. Set the following variables before running command
``` console
export ABBR=<Your Short Abbreviation, no longer than 4 characters>
export ENVIRONMENT_ABBR=<Environment Short Name>
export REGISTRY=<Image Registry + Repository FQDN Format>
```
2. Clone cf-configs repository
``` console
git clone ...
```
3. Create branch based on your abbreviation. 
``` console
git checkout -b $ABBR
```
4. Run the following command once per environment you'd like to configure after setting the Environment Variables.
``` console
cp -r workshop-templates/abbr/  environments/$ENVIRONMENT/$ABBR && cd environments/$ENVIRONMENT/$ABBR && find . -type f -name "*.yaml" -exec sed -i .bak -e "s|abbr|$ABBR|g ; s|registry-fqdn|$REGISTRY|g" {} +
```
5. Add files, commmit and push
``` console
git add .
git commit -m  "Add files for $ABBR"
git push --set-upstream origin $ABBR
```
