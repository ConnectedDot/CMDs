# Comprehensive CSS Snippets, Commands, and Code Examples  

This document provides a structured and comprehensive list of CSS snippets, commands, and code examples, organized by importance and complexity.  

## Table of Contents  
1. [Basic CSS](#basic-css)  
2. [Selectors](#selectors)  
3. [Box Model](#box-model)  
4. [Typography](#typography)  
5. [Positioning and Layout](#positioning-and-layout)  
6. [Flexbox](#flexbox)  
7. [Grid](#grid)  
8. [Transitions and Animations](#transitions-and-animations)  
9. [Responsive Design](#responsive-design)  
10. [Advanced Techniques](#advanced-techniques)  

---

## 1. Basic CSS  
### Setting Background Color  
```css  
body {  
    background-color: lightblue;  
}  
```  

### Changing Text Color  
```css  
p {  
    color: red;  
}  
```  

### Adding Borders  
```css  
div {  
    border: 1px solid black;  
}  
```  

---

## 2. Selectors  
### Universal Selector  
```css  
* {  
    margin: 0;  
    padding: 0;  
}  
```  

### Class Selector  
```css  
.my-class {  
    font-size: 16px;  
}  
```  

### ID Selector  
```css  
#my-id {  
    background-color: yellow;  
}  
```  

---

## 3. Box Model  
### Padding and Margin  
```css  
div {  
    padding: 10px;  
    margin: 20px;  
}  
```  

### Box Sizing  
```css  
div {  
    box-sizing: border-box;  
}  
```  

---

## 4. Typography  
### Font Family  
```css  
body {  
    font-family: Arial, sans-serif;  
}  
```  

### Font Size  
```css  
h1 {  
    font-size: 2em;  
}  
```  

### Line Height  
```css  
p {  
    line-height: 1.5;  
}  
```  

---

## 5. Positioning and Layout  
### Static Positioning  
```css  
div {  
    position: static;  
}  
```  

### Absolute Positioning  
```css  
div {  
    position: absolute;  
    top: 50px;  
    left: 100px;  
}  
```  

---

## 6. Flexbox  
### Basic Flexbox Container  
```css  
.container {  
    display: flex;  
    justify-content: center;  
    align-items: center;  
}  
```  

### Flex Item Properties  
```css  
.item {  
    flex: 1;  
}  
```  

---

## 7. Grid  
### Basic Grid Layout  
```css  
.container {  
    display: grid;  
    grid-template-columns: repeat(3, 1fr);  
}  
```  

### Grid Gap  
```css  
.container {  
    gap: 10px;  
}  
```  

---

## 8. Transitions and Animations  
### Simple Transition  
```css  
button {  
    transition: background-color 0.3s ease;  
}  
```  

### Keyframe Animation  
```css  
@keyframes slide {  
    from {  
        transform: translateX(0);  
    }  
    to {  
        transform: translateX(100px);  
    }  
}  

div {  
    animation: slide 2s infinite;  
}  
```  

---

## 9. Responsive Design  
### Media Query Example  
```css  
@media (max-width: 600px) {  
    body {  
        background-color: lightgray;  
    }  
}  
```  

### Fluid Typography  
```css  
h1 {  
    font-size: calc(1.5rem + 1vw);  
}  
```  

---

## 10. Advanced Techniques  
### CSS Variables  
```css  
:root {  
    --main-color: #3498db;  
}  

button {  
    background-color: var(--main-color);  
}  
```  

### CSS Grid with Named Areas  
```css  
.container {  
    display: grid;  
    grid-template-areas:  
        "header header"  
        "sidebar main"  
        "footer footer";  
}  

.header { grid-area: header; }  
.sidebar { grid-area: sidebar; }  
.main { grid-area: main; }  
.footer { grid-area: footer; }  
```  

---

This document can be expanded further as needed.  