# babel-plugin-react-jsx-directives

![npm](https://img.shields.io/npm/v/babel-plugin-react-jsx-directives)
![GitHub repo size](https://img.shields.io/github/repo-size/damianc/babel-plugin-react-jsx-directives)
![high usability](https://img.shields.io/badge/usability-%E2%98%85%20high-fa0)

Babel plugin that carries directives to React JSX:
* [`rx-if`](#the-rx-if-directive)
* [`rx-if / rx-else (rx-elseif)`](#the-rx-if-directive)
* [`rx-show`](#the-rx-show-directive)
* [`rx-hide`](#the-rx-hide-directive)
* [`rx-for`](#the-rx-for-directive)
* [`rx-switch / rx-case (rx-default)`](#the-rx-switch-directive)
* [`rx-class`](#the-rx-class-directive)
* [`rx-class-*`](#the-rx-class--directive)
* [`rx-style-*`](#the-rx-style--directive)
* [`rx-model`](#the-rx-model-directive)
* [`rx-params`](#the-rx-params-directive)
* [`rx-dynamic-prop`](#the-rx-dynamic-prop-directive)
* [`rx-dynamic-event`](#the-rx-dynamic-event-directive)

## Installation

```
npm i babel-plugin-react-jsx-directives
```

### Options

| Option | Type | Description |
|--------|------|-------------|
| `prefix` | string | A prefix directives are preceded with; must consist of one or more lowercase characters. |

#### Change of the Prefix

```
plugins: [
	['babel-plugin-react-jsx-directives', { prefix: 'x' }]
]
```

## The `rx-if` Directive

```
<p rx-if={this.state.status == 'available'}>
	I'm available
</p>
<p rx-elseif={this.state.status == 'busy'}>
	I'm busy now
</p>
<p rx-else>
	I'm certainly AFK
</p>
```

## The `rx-show` Directive

```
<div rx-show={operationPerformed}>
	Operation has finished successfully.
</div>
```

## The `rx-hide` Directive

```
<div rx-hide={errors.length === 0}>
	form contains errors
</div>
```

## The `rx-for` Directive

```
<ul>
	<li rx-for={(book, idx) in this.state.books}
		key={idx}
	>
		{idx + 1}. {book.title}
	</li>
</ul>
```

## The `rx-switch` Directive

```
<div rx-switch={this.state.n}>
	<p rx-case={1}>1</p>
	<p rx-case={2}>2</p>
	<p rx-case={3}>3</p>
	<p rx-default>?</p>
</div>
```

## The `rx-class` Directive

```
<div className="box"
	rx-class={{isError: this.state.isError, isOk: this.state.isOk}}
>...</div>
```

## The `rx-class-*` Directive

```
<div className="message"
	rx-class-fullscreen={this.state.device == 'mobile'}
>...</div>
```

## The `rx-style-*` Directive

```
<p rx-style-color={hasError ? 'red' : '#222'}>...</p>
```

```
<p rx-style-fontSize="20">...</p>
```

> You can use `rx-style-font-size`, yet the plugin will turn it into `rx-style-fontSize`, eventually.

* a unit can be specified:

```
<p rx-style-margin_px="25">...</p>
```

* use `percent` if a unit is meant to be `%`:

```
<div rx-style-width_percent="75">...</div>
```

> A unit can be specified if a value of the directive is just a string rather than expression.

## The `rx-model` Directive

* the input below is connected to the `phrase` property of a component state:

```
<input rx-model="phrase" />
```

* and this one to the `accepted` property of the state:

```
<input type="checkbox" rx-model="accepted" />
{ this.state.accepted ? 'Accepted' : 'Not accepted' }
```


## The `rx-params` Directive

The directive allows omitting callback when using render props.

* instead of callback:

```
<div user={this.state.user}>
	{(user, idx) => {
		return <p>[{ idx }] { user.name } { user.surname } ({ user.age })</p>;
	}}
</div>
```

* you can use `rx-params` directive:

```
<div user={this.state.user} rx-params={(user, idx)}>
	<p>[{ idx }] { user.name } { user.surname } ({ user.age })</p>
</div>
```

## The `rx-dynamic-prop` Directive

```
<div rx-dynamic-prop={[propToBind, valueForProp]}>
	...
</div>
```

> It's like `:[propToBind]="valueForProp"` directive known from the Vue framework.

## The `rx-dynamic-event` Directive

```
<div rx-dynamic-event={[eventToListen, eventsHandler]}>
	...
</div>
```

> It's like `@[eventToListen]="eventsHandler"` directive known from the Vue framework.