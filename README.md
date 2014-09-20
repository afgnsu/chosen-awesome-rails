# Chosen awesome (with ajax support and dynamic options injection)
====================

A written from the scratch library that wraps around default html select controls
and makes them more user friendly (Ruby on Rails package).

## Usage

### Install chosen-awesome-rails gem

Include `chosen-awesome-rails` in Gemefile

    gem 'chosen-awesome-rails'
    
Then run `bundle install`

### Include javascript assets

Add to your `app/assets/javascripts/application.js`

    //= require chosen

### Include chosen stylesheet assets

Add to your `app/assets/stylesheets/application.css`

    *= require chosen
    
You might also use twitter bootstrap integration by adding

    *= require chosen/bootstrap
    
### Enable chosen
```javascript
$("select").chosen()
```

Default options are:

```javascript
{
  allow_insertion: false, // allows to add missing options dynamically, e.g. when you
                          // need to show a list of tags allowing users to add missing ones
  inherit_classes: true,  // whether chosen should inherit html class names from the
                          // original select element
  option_parser: null,    // a function that should return an object that
                          // will be passed right to jQuery's append method to build
                          // html option elemets: $("<option />", parsed_object)
  option_formatter: null  // a function that accepts an option object (jquery selector)
                          // and returns an array of 2 values where one is used
                          // for the dropdown item and another for the choice element
}
```

The option formatter allows to build selects like this one:

![Custom dropdown options]
(http://oi60.tinypic.com/28818i8.jpg)

You can also override text messages with:

```javascript
{
  locale: {
    no_results: "No results found",
    start_typing: "Please start typing",
    add_new: "add new"
  }
}
```

And pass the next ajax options:

```javascript
{
  ajax: {
    url: "where to fetch options",
    type: "get",      // optional
    dataType: "json", // optional
    data: {},         // optional
    async: true,      // optional
    xhrFields: null   // optional
  }
}
```
