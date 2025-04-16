#  Azure pipelines variable transfer between stages and jobs

- https://medium.com/microsoftazure/how-to-pass-variables-in-azure-pipelines-yaml-tasks-5c81c5d31763

## Step access

```yaml
        steps:
          - bash: |
              MY_VARIABLE="this is my variable"
              echo "##vso[task.setvariable variable=GLOBAL_VAR;isOutput=true]$MY_VARIABLE"
            name: SetVariableStep

          - bash: |
              echo $(SetVariableStep.GLOBAL_VAR)
            displayName: 'Variable from step'
```
