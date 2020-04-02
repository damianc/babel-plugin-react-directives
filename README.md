# babel-plugin-react-jsx-directives

![npm](https://img.shields.io/npm/v/babel-plugin-react-jsx-directives)
![GitHub repo size](https://img.shields.io/github/repo-size/damianc/babel-plugin-react-jsx-directives)
![high usability](https://img.shields.io/badge/usability-%E2%98%85%20high-fa0)

Babel plugin that carries directives to React JSX:
* `rx-if`
* `rx-if / rx-else (rx-elseif)`
* `rx-for`
* `rx-switch / rx-case (rx-default)`

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

## Example of `rx-if`

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

## Example of `rx-for`

```
<ul>
	<li rx-for={(book, idx) in this.state.books}
		key={idx}
	>
		{idx + 1}. {book.title}
	</li>
</ul>
```

## Example of `rx-switch`

```
<div rx-switch={this.state.n}>
	<p rx-case={1}>1</p>
	<p rx-case={2}>2</p>
	<p rx-case={3}>3</p>
	<p rx-default>?</p>
</div>
```