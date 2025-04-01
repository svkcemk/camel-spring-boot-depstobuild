# Camel and Autobuilder

## Bacon documentation

https://project-ncl.github.io/bacon/guide/experimental.html
=======
In order to use the autobuilder, your first step is going to be generating a build-config.yaml that includes configuration of your third party dependencies.    Below describes the syntax of the config you will use to generate your pig build-config.yaml.

### Important Documentation

[Bacon Autobuild Configuration Generation](https://github.com/project-ncl/bacon/pull/1033/files?short_path=ef4470f#diff-ef4470fa0461b8c46ef23722bce4e077a52ba4629efaaffe9a3a3c7ee6f3d82b)
[Documentation for scm.yaml](https://github.com/redhat-appstudio/jvm-build-data/blob/main/README.adoc)

In order to use the autobuild dependency-generator, you need to add enableExperimental=true to your configuration profile - I added it to my ~/.config/pnc-bacon/config.yaml and that seemed to enable the experimental features.     If you do not have a config.yaml, there's a sample one in the [examples](./examples) directory that you can use (note that you need to add your Kerberos username for the username fields)

## To run the autobuilder

``bacon experimental dependency-generator generate camel-autobuilder.yaml > build-config.yaml``

will generate a config.

## To use this config

Create a location for your build config and copy the ``build-config.yaml`` file that you just generated into it. 

``mkdir -p ~/buildconfigs``

``cp build-config.yaml ~/buildconfigs``

### Invoke your build-config.yaml with pig

``bacon pig run /Users/tcunning/buildconfigs/ --skipJavadoc``

In case of errors, check the [bacon documentation](https://project-ncl.github.io/bacon/).   If you are on Mac OS X and you have not added the Red Hat Certificate to the JDK, you may need to use keytool to import it.

### Check PNC for your results

[Camel Extensions for Quarkus Third Party Components](https://orch.psi.redhat.com/pnc-web/#/products/163/versions/387)
