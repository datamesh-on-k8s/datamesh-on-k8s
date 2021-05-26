# Meeting notes

## user flow

```bash
kubectl apply -f https://blabla/datamesh.yaml
brew install kubedm
kubedm add product --name blabla --config config.yaml --namespace blabla
```

## example

CDR.yaml

```yaml
   apiVersion: datamesh.io/v1
   kind: DataProduct
   metadata:
     type: ( batch | stream )
     name: blabla
     consumers: ( productSelector* )
   spec:
     workflowSpec:
     - name: job1
       triggers: (file-drop | manual | ... )
       sources: (productSelector | pvc | nil <generator> )
       dests: (console | pvc | db | nil <blackhole> )
         owner: true | false
       jobImage:
       
     - name: job2
       triggers: job1
       sources: (productSelector | pvc | nil <generator> )
       dests: (console | pvc | db | nil <blackhole> )
         owner: true | false
       jobImage:
```

## elevator pitch

k8s native
datamesh 目前的概念与落地的抽象模型之间是有脱节的，没有提供足够好的抽象给数据产品开发者
脱离繁杂的技术选型和业界令人眼花缭乱的数据解决方案，让 produt team 更加专注在数据和数据产品上
datamesh 真正可行的落地方案，platform as a living instance

