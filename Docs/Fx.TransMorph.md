Class: Fx.TransMorph
====================

Allows per-property transitions for the animation of multiple CSS properties at once, even by a CSS selector.

### Extends:

- [Fx][]

### Implements:

- [Fx.Morph][]

### Syntax:

	var myFx = new Fx.TransMorph(element[, options]);
	
### Arguments:

1. element - (*mixed*) A string ID of the Element or an Element to apply the style transitions to.
2. options - (*object*, optional) The [Fx][] options object.

### Returns:

* (*object*) A new Fx.TransMorph instance.

### Example:

	var myEffect = new Fx.TransMorph('myElement', {duration: 'long'});

	myEffect.start({
		'height': [10, 100], //Morphs the 'height' style from 10px to 100px.
		'width': [900, 300]  //Morphs the 'width' style from 900px to 300px.
	}, {
		'width': Fx.Transitions.Elastic.easeOut //Morphs the 'width' with a cubicular transition
	});

### See Also:

- [Fx][]
- [Fx.Morph][]
- [Fx.Transitions][]



Fx.TransMorph Method: set
-------------------------

Same as [Fx.Morph][]



Fx.TransMorph Method: start
---------------------------

Executes multiple transitions for any number of CSS properties in tandem.

### Syntax:

	myFx.start(properties, transitions);

### Arguments:

1. properties - (*mixed*) An *object* of key/value pairs of CSS attributes to change or a *string* representing a CSS selector which can be found within the CSS of the page. If only one value is given for any CSS property, the transition will be from the current value of that property to the value given.
2. transitions - (*object*) An *object* of key/value pairs of transition functions or strings for each CSS attribute.

### Returns:

* (*object*) This Fx.TransMorph instance.

### Examples:

	var myEffect = new Fx.TransMorph('myElement', {duration: 1000});

	myEffect.start({
		'height': [10, 100],
		'width': [900, 300],
		'opacity': 0,
		'background-color': '#00f'
	}, {
		'width': Fx.Transitions.Elastic.easeOut,
		'background-color': Fx.Transitions.Quad.easeInOut
	});


Hash: Element.Properties
========================

see [Element.Properties](http://mootools.net/docs/core/Element/Element#Element-Properties)

Element Property: transmorph
----------------------------

### Setter

Sets a default Fx.TransMorph instance for an Element.

#### Syntax:

	el.set('transmorph'[, options]);

#### Arguments:

1. options - (*object*, optional) The Fx.TransMorph options.

#### Returns:

* (*element*) This Element.

#### Examples:

	el.set('transmorph', {duration: 'long'});
	el.morph({height: 100, width: 100}, {width: 'bounce:out'});

### Getter

Gets the default Fx.TransMorph instance for the Element.

#### Syntax:

	el.get('transmorph');

#### Arguments:

1. options - (*object*, optional) The Fx.TransMorph options. If these are passed in, a new instance will be generated.

#### Returns:

* (*object*) The Fx.TransMorph instance.

#### Examples:

	el.set('transmorph', {duration: 'long'});
	el.transmorph({height: 100, width: 100}, {width: 'bounce:out'});
	el.get('transmorph'); //The Fx.TransMorph instance.



Native: Element
===============

Element Method: transmorph
--------------------------

Animates an Element given the properties passed in.

### Syntax:

	myElement.transmorph(properties, transitions);

### Arguments:

1. properties - (*mixed*) The CSS properties to animate. Can be either an object of CSS properties or a string representing a CSS selector.  If only one value is given for any CSS property, the transition will be from the current value of that property to the value given.
2. transitions - (*object*) An *object* of key/value pairs of transition functions or strings for each CSS attribute.

### Returns:

* (*element*) This Element.

### Examples:

	$('myElement').transmorph({height: 100, width: 200}, {width: 'bounce:out'});




[Fx]: http://mootools.net/docs/core/Fx/Fx
[Fx.Morph]: http://mootools.net/docs/core/Fx/Fx.Morph
[Fx.Transitions]: http://mootools.net/docs/core/Fx/Fx.Transitions
