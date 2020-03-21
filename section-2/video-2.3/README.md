# Video 2.3

This video demonstrates what happens behind the scenes when we add an
application to Jenkins X.

## Prerequisites

To see similar pull requests in your own Jenkins configuration repository,
create your Jenkins X installation as described in Section 1, then add at
least one application as described in Video 2.1 or 2.2.

## GitOps

Every command we run that modifies the Jenkins X installation, such as adding
an application with `jx create quickstart` or `jx import`, also results in a
Git commit to our configuration repository. This configuration repository
tells Jenkins X what applications are configured and how to obtain the source
code. As we will see in the future, it also identifies what version of an
application is running in each environment.

See the video for details on how Jenkins X uses GitOps.
