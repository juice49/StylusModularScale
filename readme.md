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

## Usage

This is the most basic usage:

	@import StylusModularScale

	h1
		// Scale, Base Font Size, Ratio, Unit
		font-size modularScale(4, 16, 'golden', rem)

### Arguments

#### Scale

An integer value to scale the base font size by. Zero always equals the base font size. Provide a positive value to scale up or a negative value to scale down.

#### baseFontSize

The base font size in pixels. Unit optional; both `18` and `18px` are valid.

#### Ratio

The ratio to use for scaling. Must be either a string matching one of the predefined ratios, or a formula for a custom ratio.

#### Unit

The unit to use for type. Any CSS font size unit permitted.

### Configuration

I recommend wrapping the mixin to include your base values. This means you only have to pass in a base font size and ratio once. The setup looks like this:

	@import StylusModularScale

	// Create a new mixin that in turn calls `modularScale` with preset arguments
	ms(scale)
		modularScale(scale, 18, 'golden', rem)

	h1
		font-size ms(4)

Our redeclaration of `ms` maps to the `modularScale` mixin and always includes the config we've set.

## Install

	npm install juice49/StylusModularScale

## Todo

- Switch to a JS implemtation to improve portability and testability
- Explain config better
- Support an "important number" for double-stranded scale
- Test more rigorously; particularly rounding
- Test custom ratios
