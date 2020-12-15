<!-- Please do not edit this file. Edit the `blah` field in the `package.json` instead. If in doubt, open an issue. -->








[![json2md](http://i.imgur.com/uj64JFw.png)](#)











# json2md

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Ask me anything](https://img.shields.io/badge/ask%20me-anything-1abc9c.svg)](https://github.com/IonicaBizau/ama) [![Version](https://img.shields.io/npm/v/json2md.svg)](https://www.npmjs.com/package/json2md) [![Downloads](https://img.shields.io/npm/dt/json2md.svg)](https://www.npmjs.com/package/json2md) [![Get help on Codementor](https://cdn.codementor.io/badges/get_help_github.svg)](https://www.codementor.io/johnnyb?utm_source=github&utm_medium=button&utm_term=johnnyb&utm_campaign=github)

<a href="https://www.buymeacoffee.com/H96WwChMy" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png" alt="Buy Me A Coffee"></a>







> A JSON to Markdown converter.






If you're looking to use this on the client side, that's also possible. Check out the [`dist`](/dist) directory.












## :cloud: Installation

```sh
# Using npm
npm install --save json2md

# Using yarn
yarn add json2md
```













## :clipboard: Example



```js
const json2md = require("json2md")

console.log(json2md([
    { h1: "JSON To Markdown" }
  , { blockquote: "A JSON to Markdown converter." }
  , { img: [
        { title: "Some image", source: "https://example.com/some-image.png" }
      , { title: "Another image", source: "https://example.com/some-image1.png" }
      , { title: "Yet another image", source: "https://example.com/some-image2.png" }
      ]
    }
  , { h2: "Features" }
  , { ul: [
        "Easy to use"
      , "You can programmatically generate Markdown content"
      , "..."
      ]
    }
  , { h2: "How to contribute" }
  , { ol: [
        "Fork the project"
      , "Create your branch"
      , "Raise a pull request"
      ]
    }
  , { h2: "Code blocks" }
  , { p: "Below you can see a code block example." }
  , { "code": {
        language: "js"
      , content: [
          "function sum (a, b) {"
        , "   return a + b"
        , "}"
        , "sum(1, 2)"
        ]
      }
    }
]))
// =>
// # JSON To Markdown
// > A JSON to Markdown converter.
//
// ![Some image](https://example.com/some-image.png)
//
// ![Another image](https://example.com/some-image1.png)
//
// ![Yet another image](https://example.com/some-image2.png)
//
// ## Features
//
//  - Easy to use
//  - You can programmatically generate Markdown content
//  - ...
//
// ## How to contribute
//
//  1. Fork the project
//  2. Create your branch
//  3. Raise a pull request
//
// ## Code blocks
//
// Below you can see a code block example.
//
// ```js
// function sum (a, b) {
//    return a + b
// }
// sum(1, 2)
// ```
```











## :question: Get Help

There are few ways to get help:



 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:





## :memo: Documentation


### `json2md(data, prefix)`
Converts a JSON input to markdown.

**Supported elements**

| Type         | Element            | Data                                                                                                                     | Example                                                                                                                                          |
|--------------|--------------------|--------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `h1`         | Heading 1          | The heading text as string.                                                                                              | `{ h1: "heading 1" }`                                                                                                                            |
| `h2`         | Heading 2          | The heading text as string.                                                                                              | `{ h2: "heading 2" }`                                                                                                                            |
| `h3`         | Heading 3          | The heading text as string.                                                                                              | `{ h3: "heading 3" }`                                                                                                                            |
| `h4`         | Heading 4          | The heading text as string.                                                                                              | `{ h4: "heading 4" }`                                                                                                                            |
| `h5`         | Heading 5          | The heading text as string.                                                                                              | `{ h5: "heading 5" }`                                                                                                                            |
| `h6`         | Heading 6          | The heading text as string.                                                                                              | `{ h6: "heading 6" }`                                                                                                                            |
| `p`          | Paragraphs         | The paragraph text as string or array (multiple paragraphs).                                                             | `{ p: "Hello World"}` or multiple paragraphs: `{ p: ["Hello", "World"] }`                                                                        |
| `blockquote` | Blockquote         | The blockquote as string or array (multiple blockquotes)                                                                 | `{ blockquote: "Hello World"}` or multiple blockquotes: `{ blockquote: ["Hello", "World"] }`                                                     |
| `img`        | Image              | An object or an array of objects containing the `title`, `source` and `alt`  fields.                                     | `{ img: { title: "My image title", source: "http://example.com/image.png", alt: "My image alt" } }`                                                                   |
| `ul`         | Unordered list     | An array of strings or lists representing the items.                                                                            | `{ ul: ["item 1", "item 2"] }`                                                                                                                   |
| `ol`         | Ordered list       | An array of strings or lists representing the items.                                                                             | `{ ol: ["item 1", "item 2"] }`                                                                                                                   |
| `code`       | Code block element | An object containing the `language` (`String`) and `content` (`Array` or `String`)  fields.                              | `{ code: { "language": "html", "content": "<script src='dummy.js'></script>" } }`                                                                |
| `table`      | Table              | An object containing the `headers` (`Array` of `String`s) and `rows` (`Array` of `Array`s or `Object`s).                 | `{ table: { headers: ["a", "b"], rows: [{ a: "col1", b: "col2" }] } }` or `{ table: { headers: ["a", "b"], rows: [["col1", "col2"]] } }`         |
| `link`       | Link               | An object containing the `title` and the `source` fields.                                                                | `{ title: 'hello', source: 'https://ionicabizau.net' }

You can extend the `json2md.converters` object to support your custom types.

```js
json2md.converters.sayHello = function (input, json2md) {
   return "Hello " + input + "!"
}
```

Then you can use it:

```js
json2md({ sayHello: "World" })
// => "Hello World!"
```

#### Params

- **Array|Object|String** `data`: The input JSON data.
- **String** `prefix`: A snippet to add before each line.

#### Return
- **String** The generated markdown result.

### async

#### Params

- **Array|Object|String** `data`: The input JSON data.
- **String** `prefix`: A snippet to add before each line.

#### Return
- **Promise.\<String, Error>** The generated markdown result.














## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects
I open-source almost everything I can, and I try to reply to everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:


 - Starring and sharing the projects you like :rocket:
 - [![Buy me a book][badge_amazon]][amazon]—I love books! I will remember you after years if you buy me one. :grin: :book:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)


Thanks! :heart:
















## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

 - `@sidneys/releasenotes`
 - `@microfleet/schema2md`
 - `@best/github-integration`
 - `@cypress/schema-tools`
 - `lambda-docs-2md`
 - `jumia-travel-changelog`
 - `@cobalt-engine/change-logger`
 - `@best/store`
 - `uxcore-tools`
 - `p2doc`
 - `pantheon_site_management`
 - `react-docgen-markdown`
 - `utterance-to-markdown`
 - `gitdox`
 - `doc-cli`
 - `terraform2md`
 - `component-docs-2md`
 - `reposier`
 - `bookmark2md`
 - `rap2doc`
 - `make-postgres-markdown`
 - `describe-dependencies`
 - `gridsome-source-google-docs`
 - `kbase-components`
 - `@dschau/gatsby-source-google-docs`
 - `gatsby-source-google-docs-team`
 - `@shelex/schema-tools`
 - `mokker`
 - `postgres-markdown`
 - `joi-md-doc`
 - `rober19-config`
 - `solidity-benchmark`
 - `@bonitasoft/dependency-list-to-markdown`
 - `lggn`
 - `gatsby-source-google-docs-sheets`
 - `machine-ip`
 - `parse-google-docs-json`
 - `node-red-contrib-json2md`
 - `dokuinjs`
 - `@feizheng/react-markdown-props`
 - `@e2y/bdd-dictionary-generator`
 - `@s-ui/changelog`
 - `lab-changelog`
 - `@jswork/react-markdown-props`
 - `@gracexwho/model-card-generator`
 - `@bwagener/gridsome-source-google-docs`
 - `asm-auto-deploy`
 - `type-graphql-to-md`
 - `gatsby-source-google-docs`
 - `dargstack_rgen`I am using this library to generate documentation for my projects, being integrated with [blah](https://github.com/IonicaBizau/node-blah).











## :scroll: License

[MIT][license] © [Ionică Bizău][website]






[license]: /LICENSE
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
[badge_patreon]: https://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: https://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: https://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: https://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
