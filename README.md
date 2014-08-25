haikuson
========
Haikus Object Notation based on JavaScript Object Notation (JSON)

A data structure for transmitting haikus over the net and more.

![Mt. Fugi Japanese Woodblock Print](hiroshige_mt_fuji_seen_across_a_plain.jpg "Mt. Fugi Japanese Woodblock Print")

## Examples

the simple 
```
{
	"type": "Haikai",
	"haiku": [
		"harusame ya",
		"kuware-nokori no",
		"kamo ga naku"
	]
}
```

the more complex
```
{
	"type": "Haikai",
	"author": {
		"name": "Kobayashi Issa"
		"region": "Japan"
	},
	"title": ""
	"haiku": [
		"harusame ya",
		"kuware-nokori no",
		"kamo ga naku"
	],
	"translations": [
		{
			"language": "English",
			"haiku": [
				"spring rain--",
				"the uneaten ducks",
				"are quaking"
			],
			"translator": {
				"name": "David G. Lanoue"
			}
		}
	],
	"subjects": [
		"Weather",
		"Nature",
		"Living"
	],
	"description": "An idea of the coming spring and the survival of life through winters harness."
}
```

## The Structures

### Core Standard
The standard only expects two of three pieces to be valid haikuson. A `type`, which is always required, and either a `haiku` or `translations` or both. The `type` value must be string which is descriptive of the style of haiku. The most common of types should be "Haikai", "Haiku", and "Modernized Haiku". Most likely if the haiku is in English it will be categorized as an "Modernized Haiku", due to the fact that the 5-7-5 syllable rule in English provides a chance for far too many words for the complex, simplicity of the poetry. The `haiku` value is an array of strings, these strings should be split up by the lines of the haiku but could be split up by the two images the haiku possesses. Escaped characters such as a `\n` should not be used within a `haiku` array item.

### author
If possible, the use of the `author` member should be used to describe the attributed author of the haiku. If `author` is used. The only required child member is `name`.

```
"author": {
	"name": "Kobayashi Issa"
	"region": "Japan"
}
```

### translations
A translation allow people of other localizations to read the haiku. The benifits of using `tranlations` is that the inner `haiku` does not need to conform to any typical haiku facets, I.e. A translation's haiku does not need to follow a 5-7-5 syllable count.

```
"translations": [
		{
			"language": "English",
			"haiku": [
				"spring rain--",
				"the uneaten ducks",
				"are quaking"
			],
			"translator": {
				"name": "David G. Lanoue"
			}
		}
	],
```

## Remixing the standard
If you are interesting in supporting, adding to this standard, or have
a questions about this project feel free to star,
[fork](http://github.com/skj3gg/haikuson/fork),
or file an [issue](http://github.com/skj3gg/haikuson/issues). You
could also consider creating a project that helps compose and validate
haikuson in your favorite programming language.

## Are you serious?
absolutely not.

## Credit
[David G. Lanoue](http://haikuguy.com/) -- for your elegant explanations of haiku and life.