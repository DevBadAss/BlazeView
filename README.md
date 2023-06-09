# BlazeView

BlazeView is a lightweight, user-friendly, and fast JavaScript template engine. It provides a convenient way to render dynamic templates by replacing placeholders with actual data.

## Installation

You can install BlazeView by:

### Import as a module

```javascript

import BlazeView from 'path/to/blazeview.js';

```

## Usage

### Rendering a Template

To render a template using `BlazeView`, call the `render` method and provide the template string and the data object:

```javascript

const template = `

    <h1>Hello, {{ name }}!</h1>

    {{if isAdmin}}

        <p>Welcome, admin!</p>

    {{endif}}

    <ul>

        {{foreach items}}

            <li>{{ name }}</li>

        {{endforeach}}

    </ul>

`;

const data = {

    name: 'John',

    isAdmin: true,

    items: [

        { name: 'Apple' },

        { name: 'Banana' },

        { name: 'Orange' }

    ]

};

const renderedTemplate = BlazeView.render(template, data);

console.log(renderedTemplate);

```

The `render` method replaces placeholders ({{ key }}) in the template with the corresponding values from the data object. It also supports conditional rendering using `{{if key}}...{{endif}}` and iteration over arrays using `{{foreach key}}...{{endforeach}}` syntax.

### Template Syntax

Placeholder Replacement

Placeholders in the template are identified using double curly braces (`{{ }}`). The key inside the curly braces corresponds to a property in the data object. For example, `{{ name }}` will be replaced with the value of name property from the data object.

Conditional Rendering

You can use the `{{if key}}...{{endif}}` syntax for conditional rendering. The content inside the `{{if}}` and `{{endif}}` tags will only be rendered if the value of key is truthy. Otherwise, it will be omitted from the final output. You can also run multiple conditions.

Array Iteration

To iterate over an array in the data object, use the `{{foreach key}}...{{endforeach}}` syntax. The content inside the `{{foreach}}` and `{{endforeach}}` tags will be repeated for each item in the array. You can access the properties of each item using the dot notation, e.g., `{{ name }}`. You can also run multiple loops.

## Authors

- [@DevBadAss](https://www.github.com/devbadass)

## License

This project is licensed under the [MIT Licence](https://choosealicense.com/licenses/mit/)

