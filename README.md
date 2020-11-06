# Svelditor
Tab ui editor library for svelte.

Typescript is available. Follow the instruction [here](https://svelte.dev/blog/svelte-and-typescript).

<img src="img/output.gif" width=100%>

## Usage
Import svelditor by npm.
```
npm i svelditor
```
then in your app, you have to define components and root frame to start with.

```Svelte
<script>
import { root, Frame, Tab, components, Comp, FRM } from 'svelditor';

// import your components
import CompA from './CompA.svelte'
import CompB from './CompB.svelte'

// you will set your components here
components.set( [new Comp('CompA', CompA), new Comp('CompB', CompB)] );

// define root frame
const rootFrame = new Frame([], []);
rootFrame.tabs.push(new Tab('CompA', rootFrame.frames[0]));
root.init(rootFrame);

// options
debug.set(true);
</script>

<!-- place tabs in absolute coordinate -->
<FRM x={0} y={0} w={720} h={480} bind:f={$root}/>
```

That's all!
## Options

Colors are changable.
```js
col_frame.set('clear');
col_tab_text.set('#111111');
col_tab_dflt.set('#c5c5c5');
col_tab_actv.set('#f5f5f5');
```
<img src="img/color.png" width=100%>


You can check uuid of tab or frame 
```js
debug.set(true);
```
<img src="img/debug.png" width=100%>


## License
[MIT](LICENSE)