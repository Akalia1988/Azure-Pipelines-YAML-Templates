# Azure-Pipelines-YAML-Templates

Using YAML templates, you can define reusable content, logic, and parameters in separate templates that load into your pipeline at runtime. You can divide these templates into one of these four categories:
Stage: define a set of stages for related jobs

Job: define a collection of steps run by an agent

Step: define a linear sequence of operations for a job

Variable: alternative to hard coded values or variable groups

Example

Suppose you have a repository which needs to be automated through CI/CD pipelines with the following structure:

![image](https://user-images.githubusercontent.com/58148717/115415844-dab2b300-a1bc-11eb-9157-87b15400456a.png)

Without using a template, you will have to add the tasks to build, test, and deploy the docker image of the Node.JS API. Then you will have to perform the same tasks for the React.JS front-end

Please check out SAMPLE.YAML for additonal info.

![image](https://user-images.githubusercontent.com/58148717/115419939-5c581000-a1c0-11eb-870e-0212b85e8d96.png)

![image](https://user-images.githubusercontent.com/58148717/115420018-6ed24980-a1c0-11eb-9de5-4c111a0ce5f0.png)

Suppose that you must update the pipeline by, for example, adding unit tests or changing the SonarCloud connection. If you aren’t using a template, you must repeat the same operation for each duplicate.

By using YAML templates, you can split the pipeline into multiple, more manageable components stored in different files. The structure of the project would then be the following:

![image](https://user-images.githubusercontent.com/58148717/115420237-97f2da00-a1c0-11eb-8631-28fe0b9a49f8.png)

In this case pipeline would be:

Please check Perfect.yaml for further info.

![image](https://user-images.githubusercontent.com/58148717/115421014-3b43ef00-a1c1-11eb-8146-b742775f77b8.png)

![image](https://user-images.githubusercontent.com/58148717/115421095-4bf46500-a1c1-11eb-87bc-8c040aa6148a.png)

each of the steps dedicated to a particular activity is collected in a dedicated file.

Lets check them out in detail.

build-template.yaml

![image](https://user-images.githubusercontent.com/58148717/115421732-d210ab80-a1c1-11eb-85d9-f99e982a42f4.png)

Sonarcube-template.yaml

![image](https://user-images.githubusercontent.com/58148717/115421923-05533a80-a1c2-11eb-8d80-5be12bd57f04.png)

docker-template.yaml

![image](https://user-images.githubusercontent.com/58148717/115422166-421f3180-a1c2-11eb-8535-d2f75f446805.png)

In conclusion, YAML templates will keep your pipeline simpler to edit. This allows you to focus on application-specific tasks. However, be aware that a simple change to a template will affect all pipelines that use that template.
























