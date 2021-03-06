# Ember-mobiletouch

Ember addon for touch and gesture support in ember based mobile apps and websites.


##Installation

`npm install ember-mobiletouch`

`ember g ember-mobiletouch`

(or, as of recent changes)

`ember install:addon ember-mobiletouch`

##What's Included

This addon installs [HammerJS 2.0.4](https://github.com/hammerjs/hammer.js) and wires it into
your app as a global (Hammer).

It then sets up a single Hammer instance to manage gestures, and pushes the gestures received
through Ember's eventing system.


##Usage

```
Ember.View.extend({
  
  gestureAllow : [],
  
  gestureExclude : [],
  
  tap : function (e) {
    ;//do something!
  }

})
```

###gestureAllow

Optionally specify jQuery selectors for children of the View that can
trigger the defined gestures.


###gestureExclude

Optionally specify child elements of the View which should never
trigger the defined gestures.

**gestureAllow and gestureExclude can be used in tandem and will never filter the View itself**
**filters are not applied to non-gestures (e.g. events defined in defaultConfig.events)**


###Action helper

This triggers `myAction` on `tap`

`<div {{action "myAction"}}></div>`

This triggers `myAction` on `press`

`<div {{action "myAction" on="press"}}></div>`

###Link-to helper

Links trigger on `tap`.

`{{#link-to 'dashboard'}}Dashboard{{/link-to}}`

But this would trigger on `press`

`{{#link-to 'dashboard' eventName="press"}}Dashboard{{/link-to}}`

And this would trigger on `swipeRight`

`{{#link-to 'dashboard' eventName="swipeRight"}}Dashboard{{/link-to}}`



##Changelog

- [changelog](./CHANGELOG.md)


##Roadmap

- [roadmap](./ROADMAP.md)





**This portion outlines the details of collaborating on this Ember addon.**

### Installation

* `git clone` this repository
* `npm install`
* `bower install`

### Running

* `ember server`
* Visit your app at http://localhost:4200.

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build`

For more information on using ember-cli, visit [http://www.ember-cli.com/](http://www.ember-cli.com/).
