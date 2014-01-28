##Review site setup and symlinks*
There is nothing unique about the multisite setup. We use symlinks to access
the multisites via different domains. E.g. the folder that contains BFY is
named `dev.betterforyou.com`. So to access it at `betterforyou.com`, we have a
symlink in the sites folder that points `betterforyou.com` to
`/path/to/sites/directory/dev.betterfyour.com`.

We also use symlinks to simulate multiple sites running on the healthycoupons
microsite. These symlinks just link symbolic subdirectories back to docroot
from docroot. Drupal recognizes these directories as a Base Path and we use
that Base Path setting to determine which plan site we are viewing.

##Local setup*
See the previous discussion (Review site setup and symlinks)

##Review all modules

##Review all custom modules - line by line, make sure John understands everything.

##Email API (Used by SuperSaver app and plan sites to generate emails for coupons and recipes)

##CLIP - coupon ingestion, coupon printing*

* Ingestion is fairly straight forward. Using their feed we simply make use of
`node_add()`.
* The feed is a little wonky. Some things are encrypted, others are not. The
  structure of their XML is poorly formed and it takes about 60 seconds to
  force all of it into a usable array.
* Printing is fairly complex. The most awkward part is getting their response.
  Their response is sent via a URL param within an iframe.

##Grocery Server

##Caching, APC
We only use APC on Linkwell's rackspace site. We do not use it on Acquia. APC
is setup according to our Server Build instructions on github. The only
difference on LMS is that we are using the cacherouter module to store the
cache tables for healthycoupons in APC as well. You can see the configuration
for this in healthycoupons's settings file.

##Plan microsites - symlinks, how we get microsite variables, etc.*

##Repos: Assembla, Git, etc. - Make sure John has all of the access he needs. *

##LMS, BFY, HC.com multisite*

##SASS
I used SASS on two of my most recent themes (healthycoupons and citizens). For
both the sass files are stored in a directory named `sass` at the top level of
the theme and the CSS files are stored in a directory named `css` at the same
level. Assuming you have SASS installed in your dev envoronment, the command to
watch the `sass` directory and write changes to the `css` directory is:

    sass --watch sass:css

##Features

##Special programs and triggers (HW, DM, Mandated)*

Adam H has this documented somewhere. That might be the best place to start.

##Content assignment (Recipes, articles, offers)

##Feeds used by SuperSaver app*

##Deploying code on Acquia*

##Branching strategy and conventions*

##Acquia branches/repo… how it’s different than RS.*

##Acquia migration status, syncing RS and Acquia pre-cut-over*

##App server (CLIP report Ingestion and static asset server.)

