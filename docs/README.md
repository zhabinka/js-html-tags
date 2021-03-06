<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [make][1]
    -   [Examples][2]
-   [append][3]
    -   [Parameters][4]
    -   [Examples][5]
-   [node][6]
    -   [Parameters][7]
    -   [Examples][8]
-   [getName][9]
    -   [Parameters][10]
    -   [Examples][11]
-   [getValue][12]
    -   [Parameters][13]
    -   [Examples][14]
-   [is][15]
    -   [Parameters][16]
    -   [Examples][17]
-   [hasChildren][18]
    -   [Parameters][19]
    -   [Examples][20]
-   [children][21]
    -   [Parameters][22]
    -   [Examples][23]
-   [addChild][24]
    -   [Parameters][25]
    -   [Examples][26]
-   [toString][27]
    -   [Parameters][28]
    -   [Examples][29]
-   [map][30]
    -   [Parameters][31]
    -   [Examples][32]
-   [filter][33]
    -   [Parameters][34]
    -   [Examples][35]
-   [reduce][36]
    -   [Parameters][37]
    -   [Examples][38]

## make

Make a list of nodes

### Examples

```javascript
make(node('span', 'hello'), node('span', 'world'));
```

## append

Append node to a list of nodes

### Parameters

-   `dom`  
-   `element`  

### Examples

```javascript
const dom = make();
append(dom, node('h2', 'hello, world'));
```

## node

Make a node

### Parameters

-   `tag`  
-   `mix`   (optional, default `data.l()`)

### Examples

```javascript
node('h2', 'hello, world');
node('div', l(node('p', 'one'), node('p', 'two')));
```

## getName

Get node's name

### Parameters

-   `element`  

### Examples

```javascript
getName(node('p', 'hello, world')); // p
```

## getValue

Get node's value

### Parameters

-   `element`  

### Examples

```javascript
getValue(node('p', 'hello, world')); // hello, world
```

## is

Check if node is tag

### Parameters

-   `tagName` **[string][39]** 
-   `element`  

### Examples

```javascript
is('h3', node('h3', 'hexlet')); // true
is('h3', node('h6', 'hexlet')); // false
```

## hasChildren

Check if node has children

### Parameters

-   `element`  

### Examples

```javascript
hasChildren(node('h3', 'hexlet')); // false
hasChildren(node('div', l(node('p', 'wow')))); // true
```

## children

Get node's children

### Parameters

-   `element`  

### Examples

```javascript
const children = l(node('p', 'wow'), node('p', 'hey'));
children(node('div', children)); // [('p', 'wow'), ('p', 'hey')]
```

## addChild

Add child to node

### Parameters

-   `element`  
-   `child`  

### Examples

```javascript
const node = node('div');
addChild(node, node('p', 'html tags'));
```

## toString

Convert list of nodes to string

### Parameters

-   `elements`  

### Examples

```javascript
const tags = make(node('p', 'text'), node('p', 'text2'));
toString(tags); // <p>text</p><p>text2</p>
```

## map

Map a list of nodes

### Parameters

-   `func`  
-   `elements`  

### Examples

```javascript
map(element => {
  if (is('h2', element)) {
    return node('h3', getValue(element));
  }
  return element;
}, dom);
```

## filter

Filter a list of nodes

### Parameters

-   `func`  
-   `elements`  

### Examples

```javascript
filter(element => is('h2', element), dom);
```

## reduce

Reduce a list of nodes

### Parameters

-   `func`  
-   `init`  
-   `elements`  

### Examples

```javascript
reduce((element, acc) => acc + 1, 0, dom);
```

[1]: #make

[2]: #examples

[3]: #append

[4]: #parameters

[5]: #examples-1

[6]: #node

[7]: #parameters-1

[8]: #examples-2

[9]: #getname

[10]: #parameters-2

[11]: #examples-3

[12]: #getvalue

[13]: #parameters-3

[14]: #examples-4

[15]: #is

[16]: #parameters-4

[17]: #examples-5

[18]: #haschildren

[19]: #parameters-5

[20]: #examples-6

[21]: #children

[22]: #parameters-6

[23]: #examples-7

[24]: #addchild

[25]: #parameters-7

[26]: #examples-8

[27]: #tostring

[28]: #parameters-8

[29]: #examples-9

[30]: #map

[31]: #parameters-9

[32]: #examples-10

[33]: #filter

[34]: #parameters-10

[35]: #examples-11

[36]: #reduce

[37]: #parameters-11

[38]: #examples-12

[39]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String
