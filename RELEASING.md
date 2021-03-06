# RELEASING

1. update `GHCup.Version` module. `ghcupURL` must only be updated if we change the `_toolRequirements` type or the YAML representation of it. The version of the YAML represents the change increments. `ghcUpVer` is the current application version.

2. Update version in ghcup.cabal

3. Add ChangeLog entry

4. Add/fix downloads in `ghcup-<ver>.yaml`, then verify with `ghcup-gen check -f ghcup-<ver>.yaml`

5. Commit and git push with tag. Wait for tests to succeed and release artifacts to build.

6. Download release artifacts and upload them `downloads.haskell.org/ghcup`

7. Add release artifacts to yaml file (see point 4.)

8. Upload the final `ghcup-<ver>.yaml` to `webhost.haskell.org/ghcup/data/`.

9. Update bootstrap-haskell and symlinks on `downloads.haskell.org/ghcup`
