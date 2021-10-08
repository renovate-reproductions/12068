Reproduction for https://github.com/renovatebot/renovate/issues/12068

Renovate appears unable to upgrade `npm` in `engines` when `engine-strict=true`
is set in `.npmrc`. It seems like it decides what version of `npm` to install
before doing the upgrade, so that when it later tries to generate package-lock
with `npm i -g npm@VERSION &&` it is using the old version rather than the new
one.

See the error posted by Renovate at https://github.com/glasser/renovate-reproduction-12068/pull/3

The full logs from one run are in full-logs.txt.
