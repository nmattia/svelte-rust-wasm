# svelte-rust-wasm

An example webapp that uses [wasm-pack] and [svelte] for using Rust in the browser.

## Build

First, make sure all necessary tools are available:

```bash
# .envrc

PATH_add "$(nix-build --no-link \
    --tarball-ttl 0 \
    https://github.com/nmattia/dune/archive/master.tar.gz \
    --argstr user "$USER" --argstr path "$PWD" \
    --arg packages '[ "rustc" "cargo" "rustfmt" "nodejs" "wasm-pack" ]' \
    --arg env '[ "HOME='"$PWD"'/.home"  ]' \
    )/bin"
```

Then, build the wasm file:

```bash
cd lib && wasm-pack build
```

Then run the webapp:

```bash
cd svelte-app && npm ci && npm run dev
```


[wasm-pack]: https://github.com/rustwasm/wasm-pack
[svelte]: https://svelte.dev
