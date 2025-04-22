1. Set the following variables before running command
``` console
export ABBR=<Your Short Abbreviation, no longer than 4 characters>
export ENVIRONMENT_ABBR=<Environment Short Name>
export REGISTRY=<Image Registry + Repository FQDN Format>
```
2. Create branch based on your abbreviation. 
``` console
git checkout -b $ABBR
```
3. Run the following command once per environment you'd like to configure after setting the Environment Variables.
``` console
cp -r workshop-templates/abbr/  environments/$ENVIRONMENT/$ABBR && cd environments/$ENVIRONMENT/$ABBR && find . -type f -name "*.yaml" -exec sed -i .bak -e "s|abbr|$ABBR|g ; s|registry-fqdn|$REGISTRY|g" {} +
```
4. Push your branch to GitHub.
``` console
git add .
```
5. Push your branch to GitHub.
``` console
git commit -m "Add files for $ABBR"
```
6. Push your branch to GitHub.
``` console
git push --set-upstream origin $ABBR
```
