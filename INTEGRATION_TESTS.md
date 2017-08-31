
# Running the integrations tests 

To run the integration tests use the following steps:

## Deploy the configmap

```
oc create configmap app-config --from-file=app-config.yml
```

## Deploy the booster

```
mvn -Popenshift fabric8:deploy
```

### Run the integration tests

```
mvn -Popenshift-it verify
```

### Undeploy the booster

```
mvn -Popenshift fabric8:undeploy
```

### Undeploy the configmap

```
oc delete cm app-config
```
