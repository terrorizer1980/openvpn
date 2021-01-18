# Changes versus vanilla OpenVPN

1. Added functionality to be able to supply a auth fail reason when using deferred authentication.
   Normally, OpenVPN only supports fail reasons when using non-deferred authentication.
2. Tweaked Systemd service files to work with the mullvad OpenVPN service.

# How to upgrade to next version of OpenVPN?

1. Clone/pull this repo.

1. If you do not already have the upstream repo added:

   `git remote add upstream https://github.com/OpenVPN/openvpn.git`

1. Update the upstream master branch locally and remotely:

   `git checkout master && git pull upstream master && git push`

1. Create a new release branch from the release tag, e.g.:

   `git checkout v2.5.0 && git checkout -b mullvad-server-patches-2.5.0`

1. Cherry pick our patches from the previous release.
   Should be fairly obvious which they are.
   Fix any potential problems.

   `git cherry-pick <patch n>`

1. Push your work and ask someone to review it :)

    `git push`

Now you can see if it builds using https://github.com/mullvad/docker-build-openvpn
