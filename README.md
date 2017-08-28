# S2I HTTPD Sample Application

This is a very basic sample application repository that can be built and deployed
on [OpenShift](https://www.openshift.com) using the [s2i httpd build image](https://github.com/sclorg/httpd-container).

The application serves a single static html page via httpd.

To build and run the application:

```
$ s2i build https://github.com/eupraxialabs/httpd-ex centos/httpd-24-centos7 anhttpdimage
$ s2i build https://davidjbrewer:g\!thu33@github.com/eupraxialabs/httpd-ex centos/httpd-24-centos7 www-el:1.1
$ docker run -p 8095:8080 www-el:1.1
$ # browse to http://localhost:8095
```

You can also build and deploy the application on OpenShift, assuming you have a
working `oc` command line environment connected to your cluster already:

`$ oc new-app centos/httpd-24-centos7~https://github.com/eupraxialabs/httpd-ex`

You can also deploy the sample template for the application:

`$ oc new-app -f https://raw.githubusercontent.com/openshift/httpd-ex/master/eupraxialabs/templates/httpd.json`
