# Naked Form Select
Use this package to style form selects that adds minimal markup and requires minimal css. Naked Form Select supports single and multi-select as well as has an option to turn on keyword search. It is written in Javascript and requires no other dependencies.

## Demo
I've provided a simple demo in the [demo folder](https://github.com/developerdayo/naked-form-select/tree/master/demo).

## Quick start
• Install with npm: `npm install naked-form-select`

## Support
"browserslist": [<br />
&nbsp;&nbsp;&nbsp;&nbsp;"> 1%",<br />
&nbsp;&nbsp;&nbsp;&nbsp;"last 2 versions",<br />
&nbsp;&nbsp;&nbsp;&nbsp;"ie >= 11"<br />
]

### For IE11 Support
Include the files in the [dist/js/ie11-polyfills](https://github.com/developerdayo/naked-form-select/tree/master/dist/js/ie11-polyfills) as this plugin uses forEach and Array.from.

## Usage
### Initialize
Initialize by passing in your selector. For example: `nakedFormSelect('select')`

### Multi-select
#### How to enable
To enable multi-select, just make sure your `<select>` has the multiple property, ex) `<select multiple>`
#### Modifying multiselect verbiage
By default, in a multiselect dropdown, if one option is selected, the button/placeholder text is updated to read the selected option's text. However, if multiple options are selected, the button/placeholder text reads 'x items selected'. If you'd like to modify the keyword 'item' to say something else, add the data attribute `data-multiple-keyword` to the `select`. ex) `<select data-multiple-keyword="donut" multiple>` will read 'x donuts selected'.

### Settings Options
#### dropupThreshold
Dropup threshold indicates how many pixels away from the bottom of the window height can the dropdown button be before the dropdown list drops upwards instead of down. This is only calculated on click.

### Keyword Search
Enabling keyword search adds an input with a button to the options dropdown. The options are reduced based off of the matching characters entered into the input by the user. In addition to the 'on' option, there is also a placeholder option in which you can control the input's placeholder text.

Enable keyword search for your select by the following example:

```
  nakedFormSelect('select', {
    keywordSearch: {
      on: true,
      placeholder: 'Enter keyword'
    }
  });
```

### Context Option
Query target select elements within a certain context. This option accepts both a value and a boolean property to query document. For instance, reference
Example #4 in the demo.html file. If you want to initialize select elements with a class of .example-4 within a containing element with a class of .section-with-context, you would do so like this:
```
nakedFormSelect('.example-4', {
  context: {
    value: '.section-with-context',
    queryDocument: true
  }
});
```
This essentially accomplishes what the context parameter in jQuery selectors does.

I specifically created the 'queryDocument' option for the Drupal projects I work on to take advantage of the context variable paired with Drupal Behaviors.
So, if this option is turned on (default is 'false'), context.value will be queried intead of document.

### Default Settings
```
{
  settings = {
    dropupThreshold: 50
  },
  context = {
    value: undefined,
    queryDocument: false
  },
  keywordSearch = {
    on: false,
    placeholder: undefined
  }
}
```

## Copyright and license
Copyright (C) 2019-2020 [Sarah Ferguson](https://github.com/developerdayo).

Licensed under [the MIT license](LICENSE).