Apache MyFaces JSF implementation for WildFly packaged as Galleon feature-pack
==============================================================================

NB: You must ensure that the WildFly configuration that you are composing with the following 
layers contains the dependencies needed by the layers to properly operate. As an example, the `jsf` WildFly layers 
contain all the needed dependencies.

You can check this [Galleon maven project](https://github.com/wildfly/wildfly-s2i/wildfly-modules/jboss/container/wildfly/galleon/artifacts/opt/jboss/container/wildfly/galleon/definitions/cloud-profile-postgresql) 
that makes use of the `postgresql-datasource` layer with the WildFly `cloud-profile` to provision a custom WildFly server.

