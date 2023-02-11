# Bacon config generator

The documentation here : 

https://github.com/project-ncl/bacon/pull/1033/files?short_path=ef4470f#diff-ef4470fa0461b8c46ef23722bce4e077a52ba4629efaaffe9a3a3c7ee6f3d82b

shows how to create a config that takes a BOM and creates PNC configs for the entries in that bom that need to be productized.

In order to use this feature, you need to add enableExperimental=true to your configuration profile - I added it to my ~/.config/pnc-bacon/config.yaml and that seemed to enable the experimental features.

bacon experimental dependency-generator generate camel-autobuilder.yaml > camel-results.yaml

generates the configs.
