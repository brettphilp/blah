# Upgrading the forwarder

When deploying the data forwarder ensure that the same version of the forwarder is deployed to all clusters.

The data forwarder has the following 2 settings:

* image: densify/container-optimization-data-forwarder:4
* imagePullPolicy: Always

Updating the Image

1. Update the image tag to "4".
2. Ensure the imagePullPolicy is set to "Always"
3. Once the tag is set to the current version and with the imagePullPolicy set to "Always" the data forwarder instances will be updated automatically, if the image is updated.
