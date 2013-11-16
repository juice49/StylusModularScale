# Stylus Modular Scale

A little mixin for helping set type to a modular scale with Stylus. All of the scales from [Tim Brown's Modular Scale Calculator](http://modularscale.com/) are implemented:

- minorSecond
- majorSecond
- minorThird
- majorThird
- perfectFourth
- augFourthDimFifth
- perfectFifth
- minorSixth
- golden
- majorSixth
- minorSeventh
- majorSeventh
- octave
- majorTenth
- majorEleventh
- majorTwelfth
- doubleOctave

You can also pass your own ratio to the mixin.

The mixin is available as either `ms` or `modularScale`.

## Usage

This is the most basic usage:

	@import StylusModularScale

	h1
		// Scale, Base Font Size, Ratio
		font-size modularScale(4, 16, 'golden')
		
I recommend wrapping the mixin after importing it to include your base values. This means you only have to pass in a base font size and ratio once. The setup looks like this:

	@import StylusModularScale
	
	ms(scale)
		modularScale(scale, baseFontSize = 18, ratio = 'golden')
	
	h1
		font-size ms(4)

Our redeclaration of `ms` maps to the `ms` mixin and always includes the config we've set.

*Your redeclaration will need to call `modularScale` directly, rather than the `ms` alias.*

## Bower

	bower install StylusModularScale

## Todo

- Explain config better
- Support an "important number" for double-stranded scale
- Test more rigorously; particularly rounding