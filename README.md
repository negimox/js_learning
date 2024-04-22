# JAVASCRIPT

---

## Key Overview

- It's a dynamic programming language i.e. types( of variables, arrays, objects etc. ) are not strict they can be changed in the run-time.
- Has single threaded nature, making it bad for scalable systems. Meaning code runs line by line same happens in multi-threaded natured language but in that you are able to divide the workload among the threads.

## CLASSES

### Klasses vs Objects

Class is like a blueprint/building map, while object is like an actual thing/building.
When an class is called like `new Dog("...")` creates an object of Dog class.

### Class Syntax:

        class Animal {{
            constructor(name, legCount, speaks){
                this.name = name;
                this.legCount = legCount;
                this.speaks = speaks;
            }

            speak(){
                console.log("Hi there, " + this.speaks);
            }

            // This method/ function is not tied to the object but to this class i.e. this can be called directly on the class unlike other fn's.

            static myType(){
                console.log("Animal");
            }
        }

        let Dog = new Animal("Dog", 4, "Bhow Bhow");
        Dog.speak();
        Animal.myType();

## OBJECTS

### Converting Obj into string and vice-versa

```
const users = "{"user":"negimox", "gender":"male"}"

const decodedUser = JSON.parse(users);
console.log(decodedUser.user);

//

const stringObject = JSON.stringify(decodedUser);

```

## Function

**What's the difference between calling a function like: fn and fn()**
Calling a function in the syntax fn doesn't call it but stores the function definition.
While, fn() the function will be called and whatever that function returns it will be in the variable.

# DOM
___

## DOM Manipulation

DOM was designed to be independent of any particular programming language, making the structural representation of the document available from a single, consistent API.

### Finding HTML Elements

- **document.getElementById("ID")**
- **document.getElementByTagName("TAG")**
- **document.getElementByClassName("CLASS")**

### Finding HTML elements by CSS Selectors

- **document.querySelectorAll("CSS Selector eg{p,p.class}"):**
  <br>
  Additional selectors: https://www.w3schools.com/cssref/css_selectors.php

### Finding HTML elements by Collection

- **document.body**
- **document.anchors**
- **document.embeds**
- **document.forms**
- **document.head**
- **document.links**
- **document.scripts**
- **document.title**

### Diff b/w HTML Collection & NodeList

| document.getElementByClassName ( "CLASS" ) and document.getElementByTagName ( "TAG" ) methods return a live HTML collection.           | querySelectorAll () method returns a static NodeList.                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| A collection of document elements.                                                                                                     | A collection of document nodes (element nodes, attribute nodes, and text nodes).                                            |
| Items can be accessed by their name, id, or index number.                                                                              | Items can only be accessed by their index number.                                                                           |
| It is always a live collection. Eg: If you add a `<li>` element to a list in the DOM, the list in the HTMLCollection will also change. | Most often a static collection. Eg: if you add a `<li>` element to a list in the DOM, the list in NodeList will not change. |

### **Changing HTML Elements**

Changing HTML elements dynamically is a fundamental aspect of web development, and JavaScript provides several methods to achieve this. Here are some commonly used methods for changing HTML elements:

1.  `**innerHTML**`**:**

- **Purpose:** Changes the HTML content (including tags) of an element.

- **Example:**

```
<div class="notion-code-copy">
  <div class="notion-code-copy-button"></div></div><code class="language-javascript">
  <span class="token dom variable">document</span><span class="token punctuation">.
  </span><span class="token method function property-access">getElementById</span>
  <span class="token punctuation">(</span><span class="token string">"myElement"</span>
  <span class="token punctuation">)</span><span class="token punctuation">.</span>
  <span class="token property-access">innerHTML</span> <span class="token operator">=</span> <span class="token string">"New content"</span><span class="token punctuation">;</span></code>
```

2.  `**textContent**`**:**

- **Purpose:** Changes the text content of an element, excluding HTML tags.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token property-access">textContent</span> <span class="token operator">=</span> <span class="token string">"New text content"</span><span class="token punctuation">;</span></code>
```

3.  `**setAttribute**`**:**

- **Purpose:** Sets the value of an attribute on an element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">setAttribute</span><span class="token punctuation">(</span><span class="token string">"class"</span><span class="token punctuation">,</span> <span class="token string">"newClass"</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

4.  `**style**`**:**

- **Purpose:** Modifies the inline styles of an element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token property-access">style</span><span class="token punctuation">.</span><span class="token property-access">color</span> <span class="token operator">=</span> <span class="token string">"blue"</span><span class="token punctuation">;</span></code>
```

5.  `**classList**`**:**

- **Purpose:** Provides methods to add, remove, or toggle CSS classes on an element.

- **Examples:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token property-access">classList</span><span class="token punctuation">.</span><span class="token method function property-access">add</span><span class="token punctuation">(</span><span class="token string">"newClass"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token property-access">classList</span><span class="token punctuation">.</span><span class="token method function property-access">remove</span><span class="token punctuation">(</span><span class="token string">"oldClass"</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

6.  `**appendChild**`**:**

- **Purpose:** Adds a new child element to an existing element.

- **Example:**

```
<div class="notion-code-copy">
  <div class="notion-code-copy-button"></div></div>
  <code class="language-javascript"><span class="token keyword">var</span> newElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">createElement</span><span class="token punctuation">(</span><span class="token string">"p"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
newElement<span class="token punctuation">.</span><span class="token property-access">textContent</span> <span class="token operator">=</span> <span class="token string">"New paragraph"</span><span class="token punctuation">;</span>
<span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"parentElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">appendChild</span><span class="token punctuation">(</span>newElement<span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

7.  `**removeChild**`**:**

- **Purpose:** Removes a child element from its parent.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> childToRemove <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"childElement"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"parentElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">removeChild</span><span class="token punctuation">(</span>childToRemove<span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

8.  `**setAttribute**`**:**

- **Purpose:** Sets or changes the value of an attribute on an HTML element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myElement"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">setAttribute</span><span class="token punctuation">(</span><span class="token string">"src"</span><span class="token punctuation">,</span> <span class="token string">"new-image.jpg"</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

These methods provide a diverse set of tools for us —developers to manipulate HTML elements dynamically, whether it's updating content, changing styles, or modifying attributes. The choice of method depends on the specific requirement and the nature of the change you want to apply.

#### Example - using `**setAttribute**` to change an input field to a button:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>Change Input to Button Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>input</span> <span class="token attr-name">type</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>text<span class="token punctuation">"</span></span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>myInput<span class="token punctuation">"</span></span> <span class="token attr-name">value</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>Type Something<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>button</span> <span class="token special-attr"><span class="token attr-name">onclick</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value javascript language-javascript"><span class="token function">changeToButton</span><span class="token punctuation">(</span><span class="token punctuation">)</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>Change to Button<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>button</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token keyword">function</span> <span class="token function">changeToButton</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Get the input element</span>
            <span class="token keyword">var</span> inputElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myInput"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

            <span class="token comment">// Create a new button element</span>
            <span class="token keyword">var</span> buttonElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">createElement</span><span class="token punctuation">(</span><span class="token string">"button"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

            <span class="token comment">// Set attributes for the new button</span>
            buttonElement<span class="token punctuation">.</span><span class="token method function property-access">setAttribute</span><span class="token punctuation">(</span><span class="token string">"type"</span><span class="token punctuation">,</span> <span class="token string">"button"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
            buttonElement<span class="token punctuation">.</span><span class="token method function property-access">setAttribute</span><span class="token punctuation">(</span><span class="token string">"onclick"</span><span class="token punctuation">,</span> <span class="token string">"alert('Button Clicked!')"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
            buttonElement<span class="token punctuation">.</span><span class="token property-access">innerHTML</span> <span class="token operator">=</span> <span class="token string">"Click Me"</span><span class="token punctuation">;</span>

            <span class="token comment">// Replace the input with the new button</span>
            inputElement<span class="token punctuation">.</span><span class="token property-access">parentNode</span><span class="token punctuation">.</span><span class="token method function property-access">replaceChild</span><span class="token punctuation">(</span>buttonElement<span class="token punctuation">,</span> inputElement<span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>

<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span></code>
```

In this example, an input field with the id "myInput" is initially present, alongside a button labeled "Change to Button." Clicking this button triggers the `**changeToButton**` function, wherein a new button is dynamically created using `**createElement**`. Key attributes (type and onclick) are set via `**setAttribute**`, and the input field is promptly replaced by this newly fashioned button using `**replaceChild**`. The outcome is a dynamic transformation, demonstrating the capability to swap an input field for a button upon clicking "Change to Button," complete with an onclick attribute for interactive functionality.

### Adding HTML Elements:

1.  `**createElement**` **Method:**

- **Purpose:** Creates a new HTML element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> newElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">createElement</span><span class="token punctuation">(</span><span class="token string">"div"</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

2.  `**appendChild**` **Method:**

- **Purpose:** Appends a new child element to an existing element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> parentElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"parent"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
parentElement<span class="token punctuation">.</span><span class="token method function property-access">appendChild</span><span class="token punctuation">(</span>newElement<span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

3.  `**insertBefore**` **Method:**

- **Purpose:** Inserts a new element before a specified existing element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> existingElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"existing"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
parentElement<span class="token punctuation">.</span><span class="token method function property-access">insertBefore</span><span class="token punctuation">(</span>newElement<span class="token punctuation">,</span> existingElement<span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

4.  `**innerHTML**` **Property:**

- **Purpose:** Sets or gets the HTML content inside an element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript">parentElement<span class="token punctuation">.</span><span class="token property-access">innerHTML</span> <span class="token operator">=</span> <span class="token string">"&lt;p&gt;New content&lt;/p&gt;"</span><span class="token punctuation">;</span></code>
```

5.  `**insertAdjacentHTML**` **Method:**

- **Purpose:** Inserts HTML into a specified position relative to the element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript">parentElement<span class="token punctuation">.</span><span class="token method function property-access">insertAdjacentHTML</span><span class="token punctuation">(</span><span class="token string">"beforeend"</span><span class="token punctuation">,</span> <span class="token string">"&lt;p&gt;New content&lt;/p&gt;"</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

### Deleting HTML Elements:")Deleting HTML Elements:

1.  `**removeChild**` **Method:**

- **Purpose:** Removes a child element from its parent.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> childElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"child"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
parentElement<span class="token punctuation">.</span><span class="token method function property-access">removeChild</span><span class="token punctuation">(</span>childElement<span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

2.  `**remove**` **Method (Modern Browsers):**

- **Purpose:** Removes the element itself.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> elementToRemove <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"toRemove"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
elementToRemove<span class="token punctuation">.</span><span class="token method function property-access">remove</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

3.  `**replaceChild**` **Method:**

- **Purpose:** Replaces a child element with a new element.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> newChildElement <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">createElement</span><span class="token punctuation">(</span><span class="token string">"span"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
parentElement<span class="token punctuation">.</span><span class="token method function property-access">replaceChild</span><span class="token punctuation">(</span>newChildElement<span class="token punctuation">,</span> oldChildElement<span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

4.  `**innerHTML**` **Property (Setting to an Empty String):**

- **Purpose:** Sets the HTML content inside an element to an empty string, effectively removing its content.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript">parentElement<span class="token punctuation">.</span><span class="token property-access">innerHTML</span> <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span></code>
```

5.  `**outerHTML**` **Property:**

- **Purpose:** Replaces an element with its HTML content.

- **Example:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> newHTML <span class="token operator">=</span> <span class="token string">"&lt;p&gt;New content&lt;/p&gt;"</span><span class="token punctuation">;</span>
parentElement<span class="token punctuation">.</span><span class="token property-access">outerHTML</span> <span class="token operator">=</span> newHTML<span class="token punctuation">;</span></code>
```

## Query Selectors

Query Selectors allows developers to select and manipulate HTML elements in a document using CSS-like syntax. They provide a powerful and flexible way to target specific elements based on various criteria, such as element type, class, ID, or attribute.

Here are some common examples of using Query Selectors:

- **Selecting by Element Type:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> paragraphs <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">querySelectorAll</span><span class="token punctuation">(</span><span class="token string">'p'</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

- **Selecting by Class Name:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> elementsWithClass <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">querySelectorAll</span><span class="token punctuation">(</span><span class="token string">'.className'</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

- **Selecting by ID:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> elementWithId <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">querySelector</span><span class="token punctuation">(</span><span class="token string">'#elementId'</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

- **Selecting by Attribute:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> elementsWithAttribute <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">querySelectorAll</span><span class="token punctuation">(</span><span class="token string">'[data-custom]'</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

- **Combining Selectors:**

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> complexSelection <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">querySelectorAll</span><span class="token punctuation">(</span><span class="token string">'ul li.active'</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

Query Selectors return either a NodeList (for `querySelectorAll`) or a single element (for `querySelector`). NodeList is a collection of nodes, which can be iterated through using methods like `forEach`.

In summary, Query Selectors provide a concise and versatile way to interact with HTML elements in a document, making it easier for developers to manipulate the content and structure of a webpage dynamically.

## DOM Node & Methods

The DOM (Document Object Model) is a programming interface that represents the structure of a document as a tree of objects, where each object corresponds to a part of the document. A DOM Node is a fundamental interface in the DOM hierarchy, representing a generic node in the tree structure. All elements, attributes, and text content in an HTML or XML document are nodes.

Here are some key points about DOM Nodes and their methods:

### Key Points:

1.  **Node Types:**

- Nodes can have different types, such as elements, text nodes, attributes, comments, etc.

- The `nodeType` property is used to determine the type of a node.

2.  **Hierarchy:**

- Nodes are organized in a hierarchical structure, forming a tree.

- The `parentNode` property allows you to access the parent node of a given node.

- The `childNodes` property provides a NodeList of child nodes.

3.  **Traversal:**

- The `nextSibling` and `previousSibling` properties allow traversal to adjacent nodes.

- The `firstChild` and `lastChild` properties give access to the first and last child nodes.

### Types Of Nodes

In the DOM (Document Object Model), nodes represent different parts of an HTML or XML document, forming a tree structure. There are various types of nodes, each serving a specific purpose. Here are the common types of nodes in the DOM:

1.  **Element Nodes:**

- **Description:** Represent HTML or XML elements.

- **Access:** Accessed using methods like `getElementById`, `getElementsByTagName`, or `querySelector`.

- **Example:** The `<div>` element is an example of an element node.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>example<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>This is an element node<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span></code>
```

2.  **Attribute Nodes:**

- **Description:** Represent attributes of an HTML or XML element.

- **Access:** Attributes can be accessed through the `attributes` property of an element node.

- **Example:** In this example, `src` and `alt` are attribute nodes of the `<img>` element.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>img</span> <span class="token attr-name">src</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>example.jpg<span class="token punctuation">"</span></span> <span class="token attr-name">alt</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>Example Image<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span></code>
```

3.  **Text Nodes:**

- **Description:** Contain the text content within an HTML or XML element.

- **Access:** Accessed through the `textContent` or `innerText` property of an element node.

- **Example:** The text "This is a text node" is a text node within the `<p>` element.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>p</span><span class="token punctuation">&gt;</span></span>This is a text node<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>p</span><span class="token punctuation">&gt;</span></span></code>
```

4.  **Comment Nodes:**

- **Description:** Represent comments within the HTML or XML document.

- **Access:** Accessed through the `comment` property of a comment node.

- **Example:** The content within `<!--` and `-->` is a comment node.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token comment">&lt;!-- This is a comment --&gt;</span></code>
```

5.  **Document Node:**

- **Description:** Represents the entire document.

- **Access:** The document node is the entry point for accessing the DOM tree.

- **Example:** The `<html>` element serves as the document node in this example.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>Document Node Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>p</span><span class="token punctuation">&gt;</span></span>This is the document node.<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>p</span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span></code>
```

6.  **Document Type Node:**

- **Description:** Represents the document type declaration.

- **Access:** Accessed through the `doctype` property of the document node.

- **Example:** The `<!DOCTYPE html>` declaration is a document type node.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span></code>
```

## DOM Events

DOM events are interactions or occurrences that take place in a web page, such as a user clicking a button, pressing a key, resizing the browser window, or the content of an input field changing. The HTML DOM (Document Object Model) allows JavaScript to respond to these events, enabling developers to create interactive and dynamic web applications. Here's an overview of DOM events and how JavaScript can react to them:

#### Key Concepts:

1.  **Event Types:**

- Events can be triggered by various actions, such as mouse clicks (`click`), keyboard presses (`keydown`, `keyup`), form submissions (`submit`), document loading (`load`), and more.

2.  **Event Targets:**

- Events are associated with specific HTML elements, known as event targets. For example, a `click` event might be associated with a button, and a `change` event might be associated with a form input.

3.  **Event Handlers:**

- JavaScript can respond to events by using event handlers. Event handlers are functions that get executed when a specific event occurs.

#### Reacting to Events:

1.  **Inline Event Handlers:**

- You can define event handlers directly within HTML elements using inline attributes like `onclick`, `onmouseover`, etc.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>button</span> <span class="token special-attr"><span class="token attr-name">onclick</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value javascript language-javascript"><span class="token function">myFunction</span><span class="token punctuation">(</span><span class="token punctuation">)</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>Click me<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>button</span><span class="token punctuation">&gt;</span></span></code>
```

2.  **DOM Level 0 Event Handling:**

- You can assign event handlers directly to JavaScript properties of DOM elements.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> button <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myButton"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
button<span class="token punctuation">.</span><span class="token method-variable function-variable method function property-access">onclick</span> <span class="token operator">=</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment">// Handle the click event</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span></code>
```

3.  **DOM Level 2 Event Handling:**

- The `addEventListener` method is used to attach event handlers to elements. This method provides more flexibility and allows multiple handlers for the same event.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript"><span class="token keyword">var</span> button <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myButton"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
button<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment">// Handle the click event</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

4.  **Event Object:**

- Event handlers typically receive an event object that provides information about the event, such as the target element, mouse coordinates, key codes, etc.

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript">button<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token parameter">event</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Button clicked!"</span><span class="token punctuation">,</span> event<span class="token punctuation">.</span><span class="token property-access">target</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span></code>
```

#### Common Events:

1.  **Click Event:**

- Triggered when a mouse button is clicked.

2.  **Keydown and Keyup Events:**

- Fired when a key on the keyboard is pressed or released.

3.  **Submit Event:**

- Triggered when a form is submitted.

4.  **Change Event:**

- Fired when the value of an input field changes.

5.  **Load Event:**

- Occurs when a resource (like an image or script) and the entire page have finished loading.

#### Example:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>Event Handling Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>button</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>myButton<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>Click me<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>button</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token keyword">var</span> button <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myButton"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token comment">// Using DOM Level 2 event handling</span>
        button<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">"Button clicked!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>

<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span></code>
```

In this example, a click event handler is attached to a button using the `addEventListener` method. When the button is clicked, an alert is displayed.

Understanding DOM events and how to handle them is crucial for creating interactive and responsive web applications. Developers use events to capture user actions and trigger appropriate JavaScript functionality in response.

## The `onload` and `onunload` functions:

The `onload` and `onunload` events are part of the HTML DOM (Document Object Model) and are used to execute JavaScript code when a document or a page finishes loading (`onload`) or unloading (`onunload`). These events are commonly used to perform actions when a user enters or leaves a webpage.

### `onload` Event:

The `onload` event is triggered when a document or a webpage has finished loading. This event is often used to ensure that all resources, such as images and scripts, have been fully loaded before executing specific JavaScript code.

Example:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>onload Event Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token dom variable">window</span><span class="token punctuation">.</span><span class="token method-variable function-variable method function property-access">onload</span> <span class="token operator">=</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Code to execute after the page has fully loaded</span>
            <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">"Page loaded!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">;</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>h1</span><span class="token punctuation">&gt;</span></span>Hello, World!<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>h1</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span>
</code>
```

In this example, the `onload` event is used to display an alert when the page has finished loading.

### `onunload` Event:

The `onunload` event is triggered just before a document or a webpage is about to be unloaded, such as when the user navigates away from the page or closes the browser tab. This event is often used to perform cleanup tasks or prompt the user for confirmation before leaving the page.

Example:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>onunload Event Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token dom variable">window</span><span class="token punctuation">.</span><span class="token method-variable function-variable method function property-access">onunload</span> <span class="token operator">=</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Code to execute before the page is unloaded</span>
            <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">"Goodbye! Come back soon."</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">;</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>h1</span><span class="token punctuation">&gt;</span></span>Thanks for visiting!<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>h1</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span>
</code>
```

In this example, the `onunload` event is used to display an alert just before the page is unloaded.

These events play a crucial role in managing the lifecycle of a web page and allow developers to execute code at specific points during the page's existence.

## DOM Event Listeners

DOM Event Listeners provide a more flexible and powerful way to handle events compared to traditional event attributes (e.g., `onclick`). Event Listeners allow you to attach multiple event handlers to a single event, making your code more modular and easier to maintain.

#### Using `addEventListener`:

The `addEventListener` method is used to attach an event listener to an HTML element. It takes three parameters: the event type, the function to be executed when the event occurs, and an optional third parameter indicating whether the event should be captured during the event propagation phase.

#### Syntax:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-javascript">element<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span>eventType<span class="token punctuation">,</span> eventHandler<span class="token punctuation">,</span> useCapture<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code>
```

- `**eventType**`: A string representing the type of event (e.g., "click", "keydown", "change").

- `**eventHandler**`: A function that will be called when the event occurs.

- `**useCapture**`: (Optional) A boolean value indicating whether to use the capturing phase (`true`) or the bubbling phase (`false`, default).

#### Example of Multiple Event Listeners:

Here's a code snippet demonstrating the use of multiple event listeners on a button. In this example, we have a button that changes its color and displays a message when clicked, and it resets to its default state when the mouse leaves it:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>Multiple Event Listeners Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>style</span><span class="token punctuation">&gt;</span></span><span class="token style"><span class="token language-css">
        <span class="token selector">#myButton</span> <span class="token punctuation">{</span>
            <span class="token property">padding</span><span class="token punctuation">:</span> 10px<span class="token punctuation">;</span>
            <span class="token property">font-size</span><span class="token punctuation">:</span> 16px<span class="token punctuation">;</span>
            <span class="token property">cursor</span><span class="token punctuation">:</span> pointer<span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>style</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>button</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>myButton<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>Click me<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>button</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token comment">// Get the button element</span>
        <span class="token keyword">var</span> button <span class="token operator">=</span> <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"myButton"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token comment">// Event listener for the "click" event</span>
        button<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Change the button color</span>
            button<span class="token punctuation">.</span><span class="token property-access">style</span><span class="token punctuation">.</span><span class="token property-access">backgroundColor</span> <span class="token operator">=</span> <span class="token string">"green"</span><span class="token punctuation">;</span>
            <span class="token comment">// Display a message</span>
            <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">"Button clicked!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token comment">// Event listener for the "mouseenter" event</span>
        button<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"mouseenter"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Change the button color on mouse enter</span>
            button<span class="token punctuation">.</span><span class="token property-access">style</span><span class="token punctuation">.</span><span class="token property-access">backgroundColor</span> <span class="token operator">=</span> <span class="token string">"yellow"</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token comment">// Event listener for the "mouseleave" event</span>
        button<span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"mouseleave"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Reset the button color on mouse leave</span>
            button<span class="token punctuation">.</span><span class="token property-access">style</span><span class="token punctuation">.</span><span class="token property-access">backgroundColor</span> <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>

<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span></code>
```

In this example:

- Clicking the button changes its color to green and triggers an alert.

- Hovering over the button changes its color to yellow.

- Moving the mouse away from the button resets its color to the default state.

Using multiple event listeners allows you to handle different aspects of user interaction separately, promoting cleaner and more organized code.

## Event Bubbling & Event Capturing

Event bubbling and event capturing are two phases of event propagation in the HTML DOM. When an event occurs on an HTML element, it goes through these two phases:

1.  **Event Capturing (Capture Phase):**

- In this phase, the event travels from the root of the DOM tree to the target element.

- Event handlers attached with `useCapture` set to `true` are triggered during this phase.

2.  **Event Bubbling (Bubbling Phase):**

- In this phase, the event travels from the target element back up to the root of the DOM tree.

- Event handlers attached without specifying `useCapture` or with `useCapture` set to `false` are triggered during this phase.

### Example of Event Capturing:

In the following example, we have a nested set of div elements, and we attach event listeners to the document capturing phase (`useCapture` set to `true`). When you click on the innermost div, you'll see that the event handlers for the capturing phase are triggered from the root to the target:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>Event Capturing Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>outer<span class="token punctuation">"</span></span> <span class="token special-attr"><span class="token attr-name">style</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value css language-css"><span class="token property">border</span><span class="token punctuation">:</span> <span class="token number">1</span><span class="token unit">px</span> solid <span class="token color">red</span><span class="token punctuation">;</span> <span class="token property">padding</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token unit">px</span><span class="token punctuation">;</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>
        Outer
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>middle<span class="token punctuation">"</span></span> <span class="token special-attr"><span class="token attr-name">style</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value css language-css"><span class="token property">border</span><span class="token punctuation">:</span> <span class="token number">1</span><span class="token unit">px</span> solid <span class="token color">green</span><span class="token punctuation">;</span> <span class="token property">padding</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token unit">px</span><span class="token punctuation">;</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>
            Middle
            <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>inner<span class="token punctuation">"</span></span> <span class="token special-attr"><span class="token attr-name">style</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value css language-css"><span class="token property">border</span><span class="token punctuation">:</span> <span class="token number">1</span><span class="token unit">px</span> solid <span class="token color">blue</span><span class="token punctuation">;</span> <span class="token property">padding</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token unit">px</span><span class="token punctuation">;</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>
                Inner
            <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"outer"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Outer Capturing"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token boolean">true</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"middle"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Middle Capturing"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token boolean">true</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"inner"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Inner Capturing"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token boolean">true</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>

<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span></code>
```

When you click on the "Inner" div, you'll see in the console that the capturing phase event handlers are triggered in the order: Outer Capturing, Middle Capturing, Inner Capturing.

### Example of Event Bubbling:

In this example, event listeners are attached without specifying `useCapture` or with `useCapture` set to `false`. When you click on the innermost div, the event handlers are triggered in the bubbling phase from the target back up to the root:

```
<div class="notion-code-copy"><div class="notion-code-copy-button"></div></div><code class="language-html"><span class="token doctype"><span class="token punctuation">&lt;!</span><span class="token doctype-tag">DOCTYPE</span> <span class="token name">html</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>html</span> <span class="token attr-name">lang</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>en<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>head</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">charset</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>UTF-8<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta</span> <span class="token attr-name">name</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>viewport<span class="token punctuation">"</span></span> <span class="token attr-name">content</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>width=device-width, initial-scale=1.0<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>title</span><span class="token punctuation">&gt;</span></span>Event Bubbling Example<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>title</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>head</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>body</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>outer<span class="token punctuation">"</span></span> <span class="token special-attr"><span class="token attr-name">style</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value css language-css"><span class="token property">border</span><span class="token punctuation">:</span> <span class="token number">1</span><span class="token unit">px</span> solid <span class="token color">red</span><span class="token punctuation">;</span> <span class="token property">padding</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token unit">px</span><span class="token punctuation">;</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>
        Outer
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>middle<span class="token punctuation">"</span></span> <span class="token special-attr"><span class="token attr-name">style</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value css language-css"><span class="token property">border</span><span class="token punctuation">:</span> <span class="token number">1</span><span class="token unit">px</span> solid <span class="token color">green</span><span class="token punctuation">;</span> <span class="token property">padding</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token unit">px</span><span class="token punctuation">;</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>
            Middle
            <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>inner<span class="token punctuation">"</span></span> <span class="token special-attr"><span class="token attr-name">style</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span><span class="token value css language-css"><span class="token property">border</span><span class="token punctuation">:</span> <span class="token number">1</span><span class="token unit">px</span> solid <span class="token color">blue</span><span class="token punctuation">;</span> <span class="token property">padding</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token unit">px</span><span class="token punctuation">;</span></span><span class="token punctuation">"</span></span></span><span class="token punctuation">&gt;</span></span>
                Inner
            <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script"><span class="token language-javascript">
        <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"outer"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Outer Bubbling"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"middle"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Middle Bubbling"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

        <span class="token dom variable">document</span><span class="token punctuation">.</span><span class="token method function property-access">getElementById</span><span class="token punctuation">(</span><span class="token string">"inner"</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token method function property-access">addEventListener</span><span class="token punctuation">(</span><span class="token string">"click"</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token console class-name">console</span><span class="token punctuation">.</span><span class="token method function property-access">log</span><span class="token punctuation">(</span><span class="token string">"Inner Bubbling"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    </span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>

<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>body</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>html</span><span class="token punctuation">&gt;</span></span></code>
```

When you click on the "Inner" div, you'll see in the console that the bubbling phase event handlers are triggered in the order: Inner Bubbling, Middle Bubbling, Outer Bubbling.

In practice, event bubbling is more commonly used, and the `useCapture` parameter is often omitted or set to `false` when attaching event listeners. Event capturing is less commonly used and is mainly applicable in specific scenarios where capturing is explicitly needed.

# FEATURES
___

## Throttling and Debouncing

- Using this you can send request when user put value either input box, and the api request will automatically will be send.
- Debouncing: You don't send out the request immediately it goes after a delay. Delay the call to a function until ive not been called for 100ms
  and I've been called atleast once.
- Debounce Logic
  ```
  let timeout;
  
  function debounceSomething(){
    clearTimeout(timeout);
    timeout = setTimeout(function() {
      // Your code here.
    }, 100);
  }
  ```
- Using Debounce you can minimize the number of backend calls and optimize your application.
- Throttling: Your backend ignore few request and process the next request.
