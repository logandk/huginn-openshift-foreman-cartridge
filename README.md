# Openshift Foreman Cartridge

This cartridge for OpenShift allows you to configure and use [Foreman](https://github.com/ddollar/foreman) to run processes in the background.

This cartridge has been modified as follows:

* `foreman` is configured to run `0` web processes, so that you can use the default Passenger OpenShift Ruby setup.
* Switched to `ruby200` from `ruby193`.
* Use `bundle exec` when launching foreman.

# Installation
Once you have an existing OpenShift application, run the following command:

    rhc cartridge add -a app_name http://cartreflect-claytondev.rhcloud.com/reflect?github=ncdc/openshift-foreman-cartridge

# Usage
In the root of your application's git repository, create a file called Procfile. Then add one or more entries such as:

    mytask: bundle exec rake resque:work QUEUE=*

# Logging
Output from Foreman is written to $OPENSHIFT_HOMEDIR/foreman/log/foreman.log

# Limitations
This cartridge does not currently listen on any ports.

# License
Licensed under the Apache Software License, v2.0. Please see LICENSE for more information.
