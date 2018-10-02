# Why (and how) you should Use Emmet

## Getting Started

- Why am I writing this?
  - I just discovered Emmet and was blown away by how neat, useful and easy it is
  - I want to share it with as many people as possible
  - Check out [Emmet](https://emmet.io/)
  - Many thanks to Ray Villalobos whose [Lynda Emmet course](https://www.lynda.com/Emmet-tutorials/Coding-Faster-Emmet/133353-2.html?srchtrk=index%3a1%0alinktypeid%3a2%0aq%3aemmet%0apage%3a1%0as%3arelevance%0asa%3atrue%0aproducttypeid%3a2) inspired me

- What is Emmet?
  - Emmet is a powerful tool to enable you to write HTML and CSS rapidly, efficiently, and without irritating typos
  - In a sense, it represents shorthand for CSS/HTML
  - Highly customizable with lots of useful hotkeys, Emmet can save you time AND help you write more accurate code

- How do I get Emmet?
  - Emmet is available for a wide variety of IDEs
  - It is available in VSCode out of the box
  - Navigate [here](https://emmet.io/download/) to check availability for your favorite editor
  - **NOTE** that some of Emmet's keybindings may conflict with your editor/OS
    - Feel free to customize your IDE, OS, or Emmet's keybindings to your liking

## Core Commands

### Useful Tips

- Emmet comes with many useful commands to quickly generate html elements
- View [Emmet Syntax Docs](https://docs.emmet.io/abbreviations/syntax/) as a reference
- **NOTE** in Vscode, the command to bring up the emmet selector is `Ctrl + Space`
  - keep this in mind when editing your chained Emmet commands (more on this later)
  - Either `Enter` or `Tab` will accept the Emmet command
  - After the Emmet command is accepted, `Tab` will rotate through

### Creating Elements

- Emmet can autocreate elments with minimal syntax
- If no element is provided it will **default to a div**
  - `h1` => `<h1></h1>`
  - `video` => `<video></video>`
  - Even works for custom elements, elements from libraries, or even nonexistant elements
    - `ion-content` => `<ion-content></ion-content>`
    - `fake-element` => `<fake-element></fake-element>`

### IDs and Classes

- Same syntax as CSS selectors (`.` for class, `#` for id)
  - `#id` => `<div id="id"></div>`
  - `.class` => `<div class="class"></div>`
  - this syntax works with any element type
    - `img.img-reponsive` => `<img src="" alt="" class="img-responsive">`
  - it also works with multiple classes
    - `ion-content.item.list-item` => `<ion-content class="item list-item"></ion-content>`

### Attributes

- This feature does not responde well to punctuation inside of the square brackets
- Syntax to **set attributes** is `[attr=attributeValue]`
  - `a[href=web.site]` => `<a href="web.site"></a>`
  - works for any conceivable attribute
- Works for **multiple attributes** as well  
  - `img[src=./assets/image.jpg alt=altText]` => `<img src="./assets/image.jpg" alt="altText">`
- Very useful with Angluar/Vue directives
  - `.content[v-if=!hidden :href=url @click=function]` =>

    ```html
    <div class="content" v-if="!hidden" :href="url" @click="function"></div>
    ````

### Child, Sibling, Climb-Up

- To create a **child** of an element, use `>`
  - `div>a>img` =>

  ``` html
    <div>
      <a href="">
        <img src="" alt="">
      </a>
    </div>
  ```

- To create a **sibling** of an element, use `+`
  - `h1.header+p.description+img.img-reponsive` =>

  ```html
  <h1 class="header"></h1>
  <p class="description"></p>
  <img src="" alt="" class="img-reponsive">
  ```

- To **climb up** to an ancestor, use `^`
  - `div.row>div.col-s6+div.col-s6^div.row` =>

  ```html
  <div class="row">
    <div class="col-s6"></div>
    <div class="col-s6"></div>
  </div>
  <div class="row"></div>
  ```

### Multipliers and Numbering

- To mulitply an element, use `*number`
  - `ul.list>li.list-item*5` =>

  ```html
  <ul class="list">
    <li class="list-item"></li>
    <li class="list-item"></li>
    <li class="list-item"></li>
    <li class="list-item"></li>
    <li class="list-item"></li>
  </ul>
  ```

- To number elements, use `$`
  - Additional `$` create placeholder values
  - `ul.list>li.item$*3` =>

  ```html
  <ul class="list">
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
  </ul>
  ```

- Adding `-@` will reverse the order of the items
- Adding `@number` will cause the numbering to begin at that number

### Grouping

- Grouping items is a powerful way to ensure elements are nested in the way you intend
- Group Emmet items with `()`
  - `(.navbar>(ul.navpills>li.navlink*5>a)+.navBrand)+.mainContent` =>

  ```html
  <div class="navbar">
    <ul class="navpills">
      <li class="navlink"><a href=""></a></li>
      <li class="navlink"><a href=""></a></li>
      <li class="navlink"><a href=""></a></li>
      <li class="navlink"><a href=""></a></li>
      <li class="navlink"><a href=""></a></li>
    </ul>
    <div class="navBrand"></div>
  </div>
  <div class="mainContent"></div>
  ```
