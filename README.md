# CloudFormation

## Créer un template

- Créer un fichier de template, soit Json ou soit YAML, je préfère yaml pour simplifier le syntax

```bash
mkdir cloudformation && cd cloudformation
nano ec2_cloudformation_template.yaml
```

- Dans le fichier `yaml`, les syntax principale:

```yaml
Version: "v0.01"
Description: "Test"
Resources:
Parameters:
Mappings:
```

- [un simple EC2 stack ](.ec2_cloudformation_template.yaml)

## Créer un stack via `aws cloudformation`

- Grace au fichier template crée au dessus, on deploie tous les services de AWS en quelque seconde

- créer stack

```bash
aws cloudformation create-stack \
--template-body file://ec2_cloudformation_template.yaml \
--stack-name khacbaoanh-nguyen-template \
--parameters ParameterKey=KeyName,ParameterValue=khacbaoanh-nguyen-key \ ParameterKey=InstanceType,ParameterValue=t2.nano
```

