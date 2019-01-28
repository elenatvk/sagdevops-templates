<!-- Copyright 2013 - 2018 Software AG, Darmstadt, Germany and/or its licensors



   SPDX-License-Identifier: Apache-2.0



    Licensed under the Apache License, Version 2.0 (the "License");

    you may not use this file except in compliance with the License.

    You may obtain a copy of the License at



        http://www.apache.org/licenses/LICENSE-2.0



    Unless required by applicable law or agreed to in writing, software

    distributed under the License is distributed on an "AS IS" BASIS,

     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.

     See the License for the specific language governing permissions and



     limitations under the License.                                                  



-->



# API Gateway server



Use this template to provision and maintain API Gateway server.



## Requirements and limitations



There should not be any other packages installed on the Integration Server or Microservices Runtime instance where API Gateway is running.



### Supported Software AG releases



* API Gateway 10.1 and higher

* Command Central latest version



### Supported platforms



All supported Windows and UNIX platforms.



### Supported use cases



* Provisioning a new Integration Server or Microservices Runtime instance with API Gateway 10.1 and higher

* Installing latest fixes

* Configuration of:

  * License

  * JVM memory

  * Primary, diagnostics, and JMX ports for Integration Server or Microservices Runtime



## Using the template to provisioning a new API Gateway server instance



For information about applying templates, see [Applying template using Command Central CLI](https://github.com/SoftwareAG/sagdevops-templates/wiki/Using-default-templates#applying-template-using-command-central-cli).



To provision a new Integration Server instance named "apigateway" with API Gateway 10.3 and all latest fixes:



```bash

sagcc exec templates composite apply sag-apigateway-server nodes=node \

  is.instance.type=integrationServer \

  agw.memory.max=512 \

  repo.product=webMethods-10.3 \

  repo.fix=Empower \

  --sync-job --wait 360

```



To provision a new Microservices Runtime instance named "apigateway" with API Gateway 10.3 and all latest fixes:



```bash

sagcc exec templates composite apply sag-apigateway-server nodes=node \

  repo.product=webMethods-10.3 \

  repo.fix=Empower \

  --sync-job --wait 360

```