# My PHP WordPress Code Style

## Indentation

Always use **real tabs** and **not spaces** for indentation.

## Single and Double Quotes

Use single and double quotes when appropriate. If you’re not evaluating anything in the string, use single quotes.

```php
echo 'lorem ipsum'; // Right
echo "lorem ipsum"; // Wrong

$ipsum = 'ipsum';
echo "lorem $ipsum"; // Right
echo 'lorem ' . $ipsum; // Right
```

## Brace Style

```php
// Right
if ( $condition ) {
	action1();
}

// Wrong
if ( $condition )
{
	action1();
}
```

Don't use braces in templates.

```php
<?php if ( $condition ) : ?> <!-- Right -->
	<p>Lorem ipsum</p>
<?php endif; ?>

<?php if ( $condition ) { ?> <!-- Wrong -->
	<p>Lorem ipsum</p>
<?php } ?>
```

## Use `elseif`, not `else if`

`else if` is not compatible with the *colon syntax* for `if|elseif` blocks. For this reason, use `elseif` for conditionals.

## No Shorthand PHP Tags

Never use shorthand PHP start tags. Always use full PHP tags.

```php
<!-- Right -->
<?php action(); ?>
<?php echo $var; ?>

<!-- Wrong -->
<? action(); ?>
<?= $var ?>
```

## Remove Trailing Spaces

Remove trailing whitespace at the end of each line of code and in empty lines. Omitting the closing PHP tag at the end of a file is preferred.

## Space Usage

Always put spaces after commas.

```php
$arr = [1, 2, 3, 4]; // Right

$arr = [1,2,3,4]; // Wrong
```

Always put spaces on both sides of assignment operators.

```php
$var = true; // Right

$var=true; // Wrong
```

Always put spaces on both sides of comparison and logical operators.

```php
if ( $foo == $bar ) { ... // Right

if ( $foo==$bar ) { ... // Wrong

if ( ! $foo ) { ... // Right

if ( !$foo ) { ... // Wrong
```

Always put spaces on both sides of string concatenation.

```php
$var = $lorem . 'ipsum'; // Right

$var = $lorem.'ipsum'; // Wrong
```

When defining functions:

```php
// Right
function foo ( $bar = 1 ) {
}

// Wrong
function foo($bar=1) {
}
```

But not when calling functions:

```php
// Right
foo( $bar );

// Wrong
foo ( $bar );
```

Put spaces on both sides of the opening and closing parentheses of `if`, `elseif`, `foreach`, `for`, and `switch` blocks.

```php
// Right
if ( $condition ) {
	// ...
}

// Right
foreach ( $foo as $bar => $baz ) {
	...
}

// Wrong
if($condition){
	...
}

// Wrong
foreach($foo as $bar=>$baz) {
	...
}
```

When **type casting**, do it like so:

```php
$foo = (boolean) $bar;
```

When referring to array items, only include a space around the index if it is a variable, for example:

```php
// Right
$x = $foo['bar'];
$x = $foo[ $var ];

// Wrong
$x = $foo[ 'bar' ];
$x = $foo[$var];
```

## Arrays

Always use square bracket syntax.

```php
// Right
$arr = [1, 2, 3];
$map = [
	'foo' => 'bar'
];

// Wrong
$arr = array( 1, 2, 3 );
$map = array(
	'foo' => 'bar'
);
```

## Booleans and Null

Use lowercase versions.

```php
// Right
$var = true;
$var = false;
$var = null;

// Wrong
$var = TRUE;
$var = FALSE;
$var = NULL;
```
## Swicth block

for `switch` blocks, follow this style:

```php
switch ( $var ) {
	case 'foo': // don't put space before case colon
		action1();
	break; // break with same indentation level as his case parent

	case 'bar':
		action2();
	break;

	case 'baz':
		action3();
	break;

	default:
		action4();
}
```

## Naming Conventions

Use lowercase letters in variable, action, filter, and function names (never camelCase).

```php
function some_name ( $some_variable ) {
	$foo_bar = 1;
	...
}
```

Constants should be in all upper-case with underscores separating words:

```php
define( 'FOO_BAR', true );
```

Files should be named descriptively using lowercase letters. Hyphens should separate words.

```
my-plugin-file.php
```

Class names should use capitalized words separated by underscores. Any acronyms should be all upper case.

```php
class Bar_Baz extends Foo { ... }
class REST_API_Server { ... }
```
