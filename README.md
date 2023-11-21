```
# Only use this next command if it has already been installed and you want to run from scratch
flatpak remove --delete-data com.jagex.JagexLauncher

# Use these to build and run
flatpak remote-add --if-not-exists --user flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak-builder --install-deps-from=flathub --user --install --force-clean build-dir --disable-cache com.jagex.JagexLauncher.yml
flatpak run com.jagex.JagexLauncher

# Maintenance
If there is a new update released, you need to update the metafile url in generate_sources.py and then run that script to generate the new sources. Eventually, the fingerprint for the certificate that was used to sign the jwt will also need to be changed out once it expires.

TODO: Add in automatic updates by polling that metafile periodically.
```
