<p align="center">
  <a href="#build-framework">
  <img src="https://raw.githubusercontent.com/jetbian/build/master/.github/jetbian-logo.png" alt="Jetbian logo" width="144">
  </a><br>
  <strong>Linux Kernel Shallow Bundles</strong><br>
<br>
<a href=https://github.com/jetbian/shallow/actions/workflows/git-oras.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/jetbian/shallow/git-oras.yml?logo=linux&label=Shallow%20Linux%20bundles&style=for-the-badge&branch=master"></a>
 <br>

<br>
</p>
## Why we need this?

- Full, non-shallow clones of Linux kernel trees are multiple gigabytes in size, and take a lot of time to process.
- Shallow clones are much smaller, but cloning/fetching shallow trees impose a huge load on the git server
- `kernel.org` has [git bundles](https://git-scm.com/docs/git-bundle) available for download over HTTPS/CDN (simple file download) and [recommend their use](https://www.kernel.org/best-way-to-do-linux-clones-for-your-ci.html) - [instructions](https://www.kernel.org/cloning-linux-from-a-bundle.html) 
- This repository does the heavy lifting. Grabbing bundles, updating them from live git servers, makes them shallow and ready for consumption.
  - Produced shallow bundles are around 250 Mb as of 5.18.y
  - Produced shallow bundles include all tags for the version involved, including `-rc` tags
  - Scheduled runs update bundles daily, using GitHub actions, including caching.

Based on Armbian work.
