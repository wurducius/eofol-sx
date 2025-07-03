# eofol-sx
Dynamical JS styling library similar to styled-components

## sx (styleObj: SxStyleObject, selector?: string, prefix?: string, skipCompileCache?: boolean)

Dynamically generates on-the-fly given style and returns class name. Uses murmur32 hash for generating class names in order to cache generated styles.

### parameters:

- Object styleObj: Style in object notation known from React
- String? selector: Optional CSS Pseudo-class attached to given style
- String? prefix: Optional style definition prefix. Default value is "." which corresponds to CSS class
- Boolean? skipCompileCache: Optional parameter indicating not to register generated style to the compile cache

### returns:

String generated class name

### example usage:

```
<div class={sx({ color: "pink" })}>Pink text</div>
```

## sy (classname: string, styleObj: SxStyleObject, selector?: string, prefix?: string)

Dynamically generates given style with a particular class name.

### parameters:

- String classname: Particular class name to be generated
- Object styleObj: Style in object notation known from React
- String? selector: Optional CSS Pseudo-class attached to given style
- String? prefix: Optional style definition prefix. Default value is "." which corresponds to CSS class

### returns:

String generated class name

### example usage:

```
<div class={sy("text-pink", { color: "pink" })}>Pink text</div>
```

## syy (styleName: string, styleObj: SxStyleObject) => sy(styleName, styleObj, undefined, "")

Shorthand for sy function with usual class selector "." and empty prefix.

### parameters:

- String styleName: Particular class name to be generated
- Object styleObj: Style in object notation known from React

### returns:

String generated class name

### example usage:

```
<div class={syy("text-pink", { color: "pink" })}>Pink text</div>
```

## getCompileCache ()

Returns content of the compile cache as an array of string class names.

## clearCompileCache ()

Clears the compile cache.