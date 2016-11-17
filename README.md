# WordPress Template for OpenShift

This repo contains two templates for deploying WordPress on OpenShift using
your own copy of WordPress with any customizations you have made.

## Prerequisites

Both of the templates below are configured to use persistent volumes for
WordPress (uploads) and MySQL (data). You will need to have available
`PersistentVolume`s in your environment before deploying an application from
either template.

If you do not want to use persistent volumes, you can modify the templates
to remove the `PersistentVolumeClaim` and volume definitions for each
`DeploymentConfig`.

## Files

`wordpress-mysql-template.yaml` will deploy both WordPress and MySQL in
OpenShift with the correct items to connect them together (it does this
automatically for you)

`wordpress-template.yaml` will deploy only WordPress and requires you to
specify your database connection information for an existing database

## References

Below are some links that I used at some point as reference to build these
templates.

* https://github.com/openshift/origin/tree/master/examples/wordpress
* https://docs.openshift.com/enterprise/3.2/using_images/s2i_images/php.html
* https://github.com/WordPress/WordPress
* https://codex.wordpress.org/Editing_wp-config.php#Moving_wp-content_folder
* https://github.com/sclorg/s2i-php-container/blob/master/5.6/s2i/bin/assemble
