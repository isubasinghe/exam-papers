A)

1. To create a instance, the user first have to provide his identity to
   Keystone. After Keystone confirm the identity, it grant access for other
   services to the user. Then Glance accept requests for the NeCTAR Ubuntu-18.04
   image and their associated metadata from Swift and the image is installed by
   Nova. The network policy is set to Neutron and Neutron would provide the
   network connectivity for the instance. The cinder provide the 100Gb volume
   storage which can be mounted to the instance.
2.
3. The Glance will accept requests for disk, and the snapshot and their
   associated metadata from Swift and Nova will help create the instance with
   the snapshot. Neutron will provide network connectivity, and Cinder will
   offer volumes to the instance. All the authentication for using the resources
   and services talked above is granted by Keystone.
