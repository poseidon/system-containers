# system-containers

[System container](http://www.projectatomic.io/blog/2016/09/intro-to-system-containers/) images are OCI container images that embed systemd and runc metadata for use on Atomic host systems before high-level container runtimes are available.

Poseidon distributes `etcd`, `kubelet`, and `bootkube` system container images for use by Typhoon for Fedora Atomic. Builds pull directly from upstream container images and add only the required metadata files.

Typhoon users should not need to modify these images (you're probably in the wrong place). However, source code to build them is provided under the GPL.

## Notes

* Usage beyond Typhoon for Fedora Atomic is a non-goal
* Usage with high-level container runtimes is a non-goal
* The system container template system is intentionally not used

