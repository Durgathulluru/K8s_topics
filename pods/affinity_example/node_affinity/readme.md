Sceduler is repsonsible for deploying the pod on the node, and we can deploy the pod on the selected  node and we can do it by  selecting a **node_name** && **node_selector** 

## example of using node_name:
ex:
spec:
   nodeName: worker-node-3.example.com

## Example on how to use nodeSelectors: 

apiVersion: v1
kind: Pod
metadata: 
  name: xxxx
spec:
  nodeSelectors:
     disktype: flash
     
Before this we can label the node using 

how to label the node:

**this is where we label the node and depoy the pods on the where the labels are matching, the key values of labels helps in deploying the pod on that node**
k get no --show-labels --> will show all the labels on the node
k label node <node_name> <key=value>

*** here it comes with the afinity***
- affinty is two types
   - node affinity 
   - pod affinity
      *1. pod affinity*
       *2.pod anti_affinity*

**Definition: 
                 Affinity : Is a conditon where the requirements/condition is true then the pod get. 


k explain pod.spec.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution.NodeSelectorTerms.matchExpressions.operator
difference between:
 **condition_1:  preferredDuringSchedulingIgnoredDuringExecution: **prefered only after must requirement satisfied**

 **conditon_2: requiredDuringSchedulingIgnoredDuringExecution: **must**


## here is the example of pod.ynml ##

