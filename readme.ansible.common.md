# configuration for ansible common
 
``` yaml $(ansible)
extension-mode: experimental
# customize library used in extension. azure.cli.core by default
# cli-core-lib: azure.cli.core
 
cli:
    naming:
        default:
            singularize:
              - operationGroup
              - operation
    split-operation:
        cli-split-operation-enabled: true
        cli-split-operation-extend-poly-resource: true
    cli-directive:
        - where:
            operation: CheckNameAvailability
          hidden: true
        - where:
            operationGroup: Operations
            operation: List
          hidden: true
        - where:
            op: CreateOrUpdate
          split-operation-names:
            - Create
            - Update
    flatten:
        cli-flatten-set-enabled: true
        cli-flatten-payload: true
        cli-flatten-schema: false
        cli-flatten-all-overwrite-swagger: false
```
 

