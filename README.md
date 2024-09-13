# Crossplane

### Providers
Providers enable crossplane to provision external infrastructure. They enable all aspects to connect kubernetes with external services. i.e, Provider AWS, Provider GCP

### Managed Resources
It represents an external service in a Provider. For example, AWS EC2, AWS SNS is a managed resource. When we create a managed resource, the Provider creates external resource inside Provider's environment.

### Compositions
Compositions are a template for creating multiple managed resources as a single object. Example of composition could be;
- Combining a aws ec2, aws ebs, aws vpc configurations etc. This way, whenever we want to deploy an aws ec2 instance, we can use the composition that will have the managed resources for all the required resources to spin up ec2 instance.

### Composite Resource Definitions (XRDs)
XRDs define the schema for a custom API. Composite resources are created using API schema defined by an XRD. It is like when you create CRDs to define the custom resource.

### Composite Resources
It represents a set of managed resources as a single kubernetes object. Creating a composite resource requires XRD and composition. 

### Claims
It represents a set of managed resources as a single kubernetes object inside a namespace. 

&nbsp;

***The general workflow for using/creating all the above resources will look like;***

`Application` claims Composite Resource through -> `Claim `-> Claim interacts with `Composite Resource` -> Composite Resource composes `Managed Resources`. Composite Resource requires `XRDs` (Defines Composite Resource and Claim) and `Composition` (Configures Composite Resource).
