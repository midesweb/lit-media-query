# lit-media-query

Web component for media queries (like iron-media-query) implemented with LitElement.

## Installation

```shell
npm install lit-media-query --save
```

Then, import lit-media-query into your element:

```javascript
import lit-media-query from 'lit-media-query.js';
```

or in an html file:

```html
<script type="module" src="/path/to/lit-media-query.js"></script>
```

## Usage

In your LitElement class:
```javascript
static get properties() {
  return {
    _query: { type: String },
    _isMobile: { type: Boolean }
  }
}

constructor() {
  super();
  this._query = '(max-width: 460px)';
  this._isMobile = false;
}

render() {
  return html`
  <lit-media-query
    .query="${this._query}"
    @changed="${this._handleMediaQuery}">
  </lit-media-query>
  `;
}

_handleMediaQuery(event) {
  this._isMobile = event.detail.value;
}
```

Variable `value` from the event is a `Boolean`. Will be `true` if the media query is fulfilled, otherwise is `false`.

In this example, when the viewport is less than 460px the variable `_isMobile` will be `true`.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Changelog

### [1.0.0] - 2019-03-01
#### Added
- README.md
- LICENSE

#### Changed
- Nothing

#### Removed
- Nothing
