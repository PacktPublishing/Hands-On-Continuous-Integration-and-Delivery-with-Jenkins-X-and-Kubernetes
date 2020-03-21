# Video 4.1

This video demonstrates promoting an application to the production environment.

## Prerequisites

First install your cluster per the instruction in section 1.

## Environments and Promotion

Jenkins X uses environments to take an application through a typical
continuous delivery workflow. By default, any pull requests are deployed to
a "development" environment. Any changes to master (from a pull request or a
direct push to master) are deployed automatically to a "staging" environment.
This allows us to test the latest version before manually deploying to
"production".

To try this out, first import the application in `hello-4-1` using `jx import`.
Then, once it has finished deploying to "staging", you can test it. When you
are ready to deploy to production, run:

```
jx promote hello-4-1 --version 0.0.1 --env production
```

If you specified a different application name, or if you pushed changes to
`master`, you may need to use a different application name or version number.
You can always use `jx get applications` to see your application and figure
out what parameters to use to promote to production.

Once the promotion has succeeded, `jx get applications` will show your new
application promoted to production and let you keep track of what version has
been promoted there.
