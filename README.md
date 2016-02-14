# &lt;kwc-top-bar&gt;

> A component providing a top-bar with menus and search management.

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install kwc-top-bar --save
```

Or [download as ZIP](https://github.com/successk/kwc-top-bar/archive/master.zip).

## Usage

1 – Import polyfill:

```html
<script src="bower_components/webcomponentsjs/webcomponents-lite.min.js"></script>
```

2 – Import custom element:

```html
<link rel="import" href="bower_components/kwc-top-bar/kwc-top-bar.html">
```

3 – Start using it!

```html
<!-- Will show two menus split by an input search -->
<kwc-top-bar logo="http://placehold.it/50x50" sitename="XXX" sitehome="/" search search-placeholder="XXX" delay-search="500" delay-close-search="500" id="topbar">
  <div class="top-bar-left-menu">
    <!-- Left menu items -->
    <ul>
      <li><a href="#">XXX</a></li>
    </ul>
  </div>
  
  <div class="top-bar-right-menu">
    <!-- Right menu items -->
    <ul>
      <li><a href="#">XXX</a></li>
    </ul>
  </div>

  <div class="top-bar-search-tips">
    Tips for search
  </div>

  <div class="top-bar-search-result">
    Results of search
  </div>
</kwc-top-bar>

<script>
  //...
  listeners: {
    "topbar.search": "_doSearch"
  },
  _doSearch: function(e) {
    var query = e.detail
    // get and show results
  }
  //...
</script>
```

## Options

Attribute            | Options              | Default      | Description
---                  | ---                  | ---          | ---
`logo`               | *String*             | `null`       | URL of your logo
`sitename`           | *String*             | `null`       | Your site name
`sitehome`           | *String*             | `null`       | URL of your of page
`search`             | *boolean*            | `false`      | Show the input search
`search-placeholder` | *String*             | `null`       | The placeholder shown in input search
`delay-search`       | *number*             | `0`          | Delay before the search is triggered after last character typed
`delay-close-search` | *number*             | `0`          | Delay before the search box is closed after the user leaves the search (blur)

## Children

Selector                 | Description
---                      | ---
`.top-bar-left-menu`     | Left menu of the top-bar
`.top-bar-right-menu`    | Right menu of the top-bar
`.top-bar-search-tips`   | Tips of search
`.top-bar-search-result` | Results of search

## Methods

Method        | Parameters   | Returns     | Description
---           | ---          | ---         | ---
None          | -            | -           | -

## Events

Event       | Detail   | Description
---         | ---      | ---
search      | *String* | Trigger the search with current query. The search trigger is delayed by `delay-search`.

## Styles

Name                                   | Default          | Description
---                                    | ---              | --
`--kwc-top-bar-bg-color`               | `#fff`           | Default background color of the top-bar
`--kwc-top-bar-color`                  | `#000`           | Default text color of the top-bar
`--kwc-top-bar-box-shadow`             | `0 2px 4px #aaa` | Shadow under the top-bar
`--kwc-top-bar-site-width`             | `250px`          | Width of the site name part (logo and text)
`--kwc-top-bar-site-bg-color`          | `#fff`           | Background color of the site name
`--kwc-top-bar-site-color`             | `#000`           | Text color of the site name
`--kwc-top-bar-height`                 | `50px`           | Height of the top-bar
`--kwc-top-bar-link-menu-styles`       | `{}`             | Styles of links of menus
`--kwc-top-bar-link-menu-hover-styles` | `{}`             | Styles of links of menus when hover
`--kwc-top-bar-search-styles`          | `{}`             | Style of the input search

## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

1 – Install [bower](http://bower.io/) & [polyserve](https://npmjs.com/polyserve):

```sh
$ npm install -g bower polyserve
```

2 – Install local dependencies:

```sh
$ bower install
```

3 – Start development server and open `http://localhost:8080/components/kwc-top-bar/`.

```sh
$ polyserve
```

## History

For detailed changelog, check [Releases](https://github.com/successk/kwc-top-bar/releases).

## License

MIT