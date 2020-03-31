# babel-plugin-react-jsx-directives

![npm](https://img.shields.io/npm/v/babel-plugin-react-jsx-directives)
![NPM](https://img.shields.io/npm/l/babel-plugin-react-jsx-directives)
![GitHub repo size](https://img.shields.io/github/repo-size/damianc/babel-plugin-react-jsx-directives)
<br/>
![GitHub top language](https://img.shields.io/github/languages/top/damianc/babel-plugin-react-jsx-directives)
![GitHub last commit](https://img.shields.io/github/last-commit/damianc/babel-plugin-react-jsx-directives)
![npm (prod) dependency version](https://img.shields.io/npm/dependency-version/babel-plugin-react-jsx-directives/babel-types)
![high usability](https://img.shields.io/badge/usability-%E2%98%85%20high-fa0)

Babel plugin that carries directives to React JSX:
* `$if`
* `$if / $else`

## Installation

```
npm i babel-plugin-react-jsx-directives
```

## Example use

```
<div $if={this.state.showHello}>
    Hello
</div>
<div $else>
    yo
</div>
```