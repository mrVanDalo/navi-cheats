# navi cheats

You need [navi](https://github.com/denisidoro/navi).

For nix you use [NUR](https://github.com/nix-community/nur)
and find the package [here](https://nix-community.github.io/nur-search/repos/mrvandalo/).

## small script

I use this script because navi is a bit flaky under nix.

```
(pkgs.writers.writeBashBin "cheat" ''
  set -eu -o pipefail
  output=$( ${nur.repos.mrVanDalo.navi} --print --path "$HOME/.cheats:${nur.repos.mrVanDalo.navi}/share/navi/cheats" )
  echo "$output"
  ${pkgs.bash}/bin/bash -c "$output"
'')
```

