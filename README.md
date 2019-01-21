## 🚨 Pre-alpha 🚨

Warning: the `vf-child-template` is pre-alpha, things will change. We welcome usage and feedback, but updates will be tricky.


# Visual Framework Child template

tl;dr Clone and edit me.

This is a child template to use [the core Visual Framework (`vf-core`)](https://github.com/visual-framework/vf-core#visual-framework-20)
patterns, override them and add your own.

Why use a child? Programatically use (and update from)
Visual Framework core patterns, but with complete flexibility in the look
and function of your patterns (in addition to the Visual Framework's [style
isolation principles](https://blogs.embl.org/communications/2018/09/12/faster-scientific-websites-through-reusability/)).

## 🚼 Know the basics

If you've not already, take a few minutes to [read the basics of the Visual Framework](https://github.com/visual-framework/vf-core#visual-framework-20).

## 1️⃣ 📦 Clone the Visual Framework Child template

*(You'll need gulp and node; [head here if you don't know what those are](https://github.com/visual-framework/vf-core/blob/develop/SETTINGUP.md))*

- `git clone https://github.com/khawkins98/vf-child-playground.git` (add repo url once ready)
- `cd vf-child-playground`
- `npm install`

## 2️⃣ 🎫 Decide on project name, namespace

Open `pacakage.json` and edit:

```
"vfConfig": {
  "vfName": "Visual Framework Child pattern library",
  "vfNamespace": "vct-"
},
```

- `vfName` examples:
  - My Company Name pattern library
  - Visual Framework for My Company Name
- `vfNamespace` prefix:
  - Custom patterns will be prefixed by a short abbreviation or phrase. So, your
    custom pattern for a countdown timer might be `acme-countdown-timer` or if you're
    building for Bob's Pizza, `bp-countdown-timer`. We'd encourage you to make it:
    - unique
    - no longer than four letters

## 3️⃣ ⌨️ Launch the local pattern library

Enter `gulp dev` and the pattern library will build and open in your browser.
Be sure to keep an eye on the console for any compile errors or style linting.

## 4️⃣ 🖌 Make and edit patterns

### Override `vf-core` patterns

1. If you haven't already, install the pattern via `npm`
    - `npm install --save @visual-framework/vf-heading`
1. Move a pattern's source folder from `./components/vf-core-patterns` to `./components`
    - `mv components/vf-core-patterns/vf-heading components/vf-heading`
1. If the pattern is present in `package.json` remove its reference
    - Delete: `    "@visual-framework/vf-heading": "0.0.21",`
1. Edit the pattern in `./components` as you see fit

### Install additional patterns

You can install patterns from vf-core or from other Visual Framework-compliant pattern libraries.

To add additional Visual Framework core patterns, find one you like and use npm;
for example, the `vf-heading` pattern:

```
npm install --save @visual-framework/vf-heading
```

If a pattern you wish to use isn't available on npm, copy it to your `/components`
directory.

In either case, after adding the pattern you'll needed to reference the Sass in
your `/components/vf-core/index.scss`

### Create new patterns

This codebase includes a folder and file creation tool. It allows you to quickly create all the required files to make a component. It gives you the option to create am element, block, or container.

1. Install Yeoman
   - If you've come this far and you don't have `yo`, you should be able to install it with `npm install -g yo@latest`
   - If you get stuck, [see the official install guide](http://yeoman.io/codelab/setup.html)
1. Create a new component
   - Run `gulp component` and answer the questions when prompted.
       - **Type of component:** We use a variation of the atomic design methodology, [read about the differences here](http://bradfrost.com/blog/post/atomic-web-design/#atoms). We use: elements, blocks, and containers.
           - an element would be a heading, or a button
           - a block would be a teaser, or a search form
           - a container would be a group of teasers
       - **Name of component:** Go for something simple and obvious (todo: we need a guide/documentation on how we name things). Don't worry about namespacing and prefixing, the tooling will take care of this.
       - **NPM package:** If you're making something interesting (probably not an 'element'), then saying 'yes' will allow the component to be shared as an optional part of the framework on NPM.
    - You customised template pattern will have been added to your `/components` directory.
1. Add the `@import 'vfc-your-pattern.scss';` to `/components/vf-core/index.scss`.
1. Developing your component
   - Edit your template files in the `/components/your-pattern-name` folder
   - Run `gulp dev` to compile and preview the pattern
1. Sharing you component back
   - Publish it to npm; or
   - If you think your pattern is of use to the wider `vf-core` community, [make a Pull Request](https://github.com/visual-framework/vf-core/pulls).

## 5️⃣ 💅 Customise the pattern library

The Visual Framework uses the [Fractal pattern library](https://fractal.build/).

You can customise the layout of the pattern library by editing the Fractal theme
in `tools/frctl-mandelbrot-vf-subtheme`.

For more guidance, [see the Fractal documentation](https://fractal.build/guide/customisation/web-themes.html#configuring-themes).

## 6️⃣ 🏎 Put your pattern library into use

Once you've configured your pattern library, selected patterns and made a few new ones,
here's how you make use of them.

### Generate CSS and JS for your website

Running `gulp build` will generate a `/build` directory where you'll find:
- global assets
    - `css/styles.css`
    - `scripts/scripts.js`
- per-pattern JavaScript and image assets
    - `assets/vf-*`

### Consume patterns as Sass

You can `@import` your sass, follow the example in `components/vf-core/index.scss`.

### Deploy your pattern library

To come.

### Keeping you pattern template up to date

The `vf-child-template` follows the [`vf-core` versioning](https://github.com/visual-framework/vf-core#versioning), that means you shouldn't have to update very often; that said:

1. Most improvements will be found by updating VF patterns, to see what updates are available: `npm outdated`
1. Watch for [new releases of `vf-child-template`](https://github.com/visual-framework/vf-child-template/releases). We'll provide guidance on how to update.
1. Any updates will be easier if you're using a git repository, you are doing that, right?

## 7️⃣ 🎁 Contribute your Patterns

To come: how to add patterns back to the global `vf-core`

## 8️⃣ ⁉️ Ask the community

- [Slack](https://embl-vf.slack.com/messages)
- [GitHub issues](https://github.com/visual-framework/vf-core/issues/)
