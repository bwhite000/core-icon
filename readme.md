CoreIcon
========

A collection of core custom elements not requiring a Polymer overhead inspired by the
[Google Polymer project by the similar name](https://www.polymer-project.org/0.5/docs/elements/core-ajax.html),
but with a bunch of optimization and pruning for a slimmer implementation. This is a
Dart package that can be imported into other Dart or JS projects to add some custom elements.

Some pieces are similar to, and others are roughly based on Google's base concepts.
Don't think of it as a rehash, but a bwhite000 mod built from scratch (besides the
SVGs scraped and cleaned for the core-icons).

This is an exciting, learning side project that will have more good improvements soon!

Example
-------

Follow these sample files in your Dart or JS project to include the CoreElements package:

__pubspec.yaml__ - Add the package as a dependency.

````yaml
...
dependencies:
  core_elements:
    git: git://github.com/bwhite000/core-icon.git
````

__web/index.html__ - Setup the imports and scripts.

```html
<!doctype html>
<html>
    <head>
        <title>Core Elements Demo</title>
        
        <import rel="import" href="packages/core_icon/core_icon.html" />
        
        <script type="application/dart" src="main.dart" defer></script>
    </head>
    <body>
        <core-icon icon="default.home"></core-icon>
    </body>
</html>
```

__web/main.dart__ - Activate/register the custom elements.

```dart
import "dart:html";
import "package:core_icon/core_elements.dart" as coreIcon;

void main() {
  // Register the custom elements with the Document.
  coreIcon.registerWithDom();

  // Create the Element.
  final coreIcon.CoreIcon coreIcon = new Element.tag('core-icon')
      ..icon = 'default.home';

  // Add it to the Body to see it.
  document.body.nodes.add(coreIcon);
}
```

Compatibility
-------------

This project relys on native Browser support for:
* [HTML Imports](http://caniuse.com/#feat=imports)
* [Templates](http://caniuse.com/#feat=template)
* [Shadow DOM](http://caniuse.com/#feat=shadowdom)
* [Custom Elements](http://caniuse.com/#feat=custom-elements)
