## Reproducible Remote Environment Testing
 
>Note: Execute all commands from the examples in the main directory of repository.

To install chart with Remote Environment E2E test, execute following command:
```bash
helm install --name re-test --namespace kyma-system ./re-test/
```

then install the test executor by following command:
```bash
kc create -f scripts/tester.yaml
```
