# AIoTES deployment

This repository contains the necessary files for the deployment of AIoTES using Portainer. This includes the docker-compose file for portainer, the App templates and the corresponding docker-compose files for the stacks.


## Deployment

Before deploying Portainer, edit the values of the environment variables in the docker-compose.yml file:
+ AIOTES_HOSTNAME: DNS name the machine where AIoTES is deployed.
+ AIOTES_API_PORT: TCP port for the AIoTES API (default value 8081, do not use ports 80 or 8080).
+ AIOTES_SYSADMIN_EMAIL: email of the system admin.


For more information, see [deployment of AIoTES components using Portainer](https://github.com/activage/AIOTES-2.0/wiki/Deployment#aiotes-components-deployment).



## Customization

To customize your App templates, edit the templates.json file and then build a Docker image to host the templates using the provided Dockerfile.


To build a Nginx container to serve the AIoTES templates, use:


`docker build -t docker-activage.satrd.es/aiotes-portainer-templates:2.0 .`


To check that everything is OK, you can run the image using:


`docker run -d -p "8080:80" portainer-templates`


The templates definitions will be available at http://docker-host:8080/templates.json


To deploy this image along with Portainer, you can edit the docker-compose file.




## Further information

[Official Portainer documentation](https://www.portainer.io/documentation/).


[Portainer templates documentation](https://www.portainer.io/documentation/how-to-use-templates/).



## License

Licensed under [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0).
