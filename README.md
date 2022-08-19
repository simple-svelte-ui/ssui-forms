# Simple svelte ui - Forms components

Native HTML forms component enhanced with design to provide easy integration with Svelte.

## Installation

install with npm:

```bash
npm install @simple-svelte-ui/forms
```

install with yarn:

```bash
yarn add @simple-svelte-ui/forms
```

## Components and usage

- colors avaliable in the library:

```js
 primary    : initial
 secondary  : #6200ee
 success    : #467d32
 info       : #17a2b8
 error      : #b70000
 warning    : #caad1d
 disabled   : #80787c
```

**Note:** when `disabled` color is used element will be also disabled from any further actions

- sizing avaliable for components

```js
    small:
        font-size: 0.875rem , line-height:1.25rem

    normal:
        font-size: 1rem , line-height:1.5rem

    large:
        font-size: 1.125rem, line-height:1.75rem
```

- and when outline is set fo false only a bottom line is visible

## 1. Input

The input component is a basic input field with customization features.

```js
<script>
    import { Input } from '@simple-svelte-ui/forms';
    let value;
</script>
<input
    bind:value
    width="280px"
    color="primary"
    placeholder="Enter the value"
    icon="bx bx-color"
    size="normal"
    outline="{true}"
/>
```

- `<i>` tag is used to display icons
- actions avaliable are: `on:blur`
  `on:change`
  `on:click`
  `on:focus`
  `on:keydown`
  `on:keypress`
  `on:keyup`
  `on:mouseover`
  `on:mouseenter`
  `on:mouseleave`
  `on:paste`

## 2. Float input

Input component feild with floating label

```js
<script>
    import { FloatInput } from '@simple-svelte-ui/forms';
    let value;
</script>
<FloatInput
    bind:value
    width="280px"
    color="primary"
    placeholder="Enter the Name"
    label="Name"
    size="normal"
    outline="{true}"
/>
```

- actions avaliable are: `on:blur`
  `on:change`
  `on:click`
  `on:focus`
  `on:keydown`
  `on:keypress`
  `on:keyup`
  `on:mouseover`
  `on:mouseenter`
  `on:mouseleave`
  `on:paste`

## 3. Checkbox

To recive multipe selected options from the user

```js
<script>
    import { Checkbox } from '@simple-svelte-ui/forms';
    let checked;
</script>
<Checkbox color="primary"> Option 1</Checkbox>
```

- actions avaliable are: `on:blur`
  `on:change`
  `on:click`
  `on:focus`
  `on:keydown`
  `on:keypress`
  `on:keyup`
  `on:mouseover`
  `on:mouseenter`
  `on:mouseleave`
  `on:paste`

## 4. Radio

To select single value from multiple options, it uses flex to align the items.so `row` and `column` direction options are avaliable. `space` option is used to give space between items in `column` alignment

```js
<script>
    import {Radio} from '@simple-svelte-ui/forms' ;
    let group;
    let options =[
        'radio1',
        'radio2',
        'radio3'
        ]
</script>
<Radio
    bind:group
    list={options}
    direction="column"
    space="auto"
    color="primary"
/>
```

- actions avaliable are: `on:blur`
  `on:change`
  `on:click`
  `on:focus`
  `on:keydown`
  `on:keypress`
  `on:keyup`
  `on:mouseover`
  `on:mouseenter`
  `on:mouseleave`
  `on:paste`

## 5. LayoutRadio

Its an advance radio element with capability fof displaying an image , a heading and a description

```js
<script>
    import {LayoutRadio} from '@simple-svelte-ui/forms'
    let group
    const options=[
        {
            name:"Name",
            desc:"Description",
            img:"Image url or Local image"
        }
    ]
</script>
<LayoutRadio list={options} width="500px" bind:group />
```

- actions avaliable are: `NIL`

## 6. Range

Single headed range slider to slide for values within a range

```js
<script>
    import {Range} from '@simple-svelte-ui/forms'
    let value
</script>
<Range
    bind:value
    id="range"
    min='1'
    max='10'
    step='1'
    color="primary"
/>
```

- actions avaliable are:
  `on:change`
  `on:click`
  `on:keydown`
  `on:keypress`
  `on:keyup`

## 7. Toggle

Custom checkbox with toggle switch animation

```js
<script>
    import {Toggle} from '@simple-svelte-ui';
    let checked;
</script>
<Toggle
    bind:checked
    size="normal"
    color="primary"
    duration="100ms"
/>
```

- actions avaliable are: `on:click`
