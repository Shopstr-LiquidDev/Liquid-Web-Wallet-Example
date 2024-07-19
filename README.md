
# Liquid web wallet

**NOTE: only a mock up for now**

A [Liquid](https://liquid.net) web wallet that runs in the browser. 

![image](https://github.com/user-attachments/assets/146f3474-5255-4609-a92c-79eb5600d89a)

Watch-only mode works in any modern browser, connection with [JADE](https://blockstream.com/jade/) requires web serial and works on chrome, chromium, edge.

Based on [LWK wasm](https://github.com/Blockstream/lwk/tree/master/lwk_wasm)

![image](https://github.com/user-attachments/assets/7f341de4-0bf6-43e2-9a21-475b06f671d6)




## Try locally

Requirements:

* npm
* wasm-pack

With nix install those with `nix-shell`

Execute once (and every time to update lwk_wasm dep):

```shell
$ npm install
```

Then

```shell
$ npm run start
```

## Deploy


```shell
$ npm run build
```

Copy `dist` folder to the web server

## Avoid ids

When possible avoid ids, use web components as "namespace" and querySelector on html elements, in case of multiple elements use querySelectorAll and maps in the js class

## ADR

- Avoid js frameworks, use vanilla JS and web standards
- Use only lwk_wasm as npm dep
- Keep it simple and maintainable
- No images and almost no custom css, only picocss
- encapsulate logics in web components
- Global state, but every web component is in charge of itself, use events to communicates changes to other
- Most html stay in a `.html` -> use html templates
