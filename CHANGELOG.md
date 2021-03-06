## Docma Change-Log
---

#### **v1.1.1** Release (2016-08-13)

- Fixed an anchor/linking issue which prevented some browsers (such as Safari) to navigate properly.

#### **v1.1.0** Release (2016-08-12)

- <p>**Docma** (Builder):</p>
    + Constructors would still show up in the documentation even though `@private` is set. Fixed by `jsdoc-x`.
    + Updated dependencies to their latest versions.
    + Minor revisions.

- <p>**Default Template**:</p>
    + Fixed sidebar header/search position when sidebar is collapsed.
    + An access badge is shown next to symbol name, if symbol has `private` or `protected` access.
    + Clean up.

#### **v1.0.3** Release (2016-06-27)

- **Docma** (Builder): Added HTML source file support. You can include HTML files together with JS and markdown files while building your documentation.
- **Default Template**: Removed YAML syntax highlighting support because of incorrect auto-detection. Opened an issue [here](https://github.com/isagalaev/highlight.js/issues/1213).

#### **v1.0.1** Release (2016-06-11)

- Fixed missing web components.
- David considers [marked][marked] as [insecure dependency][docma-david]. This is [already](https://nodesecurity.io/advisories/marked_content-injection) [reported](https://github.com/chjj/marked/pull/592).

#### **v1.0.0** Release (2016-06-11)

- <p>**Docma** (Builder):</p>
    + Convert markdown files to HTML. See documentation.
    + Added `.markdown:Object` build configuration options. (Same as `marked` module options).
    + Added `.markdown.tasks:Boolean` option for parsing GitHub-like markdown tasks.
    + Added emoji (twemoji) support for converted markdown files. Added `.markdown.emoji:Boolean` option.
    + Improved GFM parsing.  
    + Added `.app.server` build option that defines the server/host type for generating server config file(s) for the SPA. e.g., setting to `"apache"` generates an `.htaccess` file within the root of the generated output. Supports `"apache"` and `"github"`.
    + Added `.app.base:String` build option that sets the base path for the SPA.
    + Added `.app.entrance:String` build option that sets the initial content to be displayed.
    + Added `.debug:Boolean` build option.
    + Dropped `.dump` config option in favor of `.debug` option.
    + Moved `.template.document` configuration to `.app`.
    + Group `.js` files into multiple, separate documentation. See `.src` build option.
    + Rename routes generated markdown files (names). See `.src` build option.
    + Added negated glob support (that excludes the paths) for the `src` build option.

- <p>**Docma Web Core**:</p>
    + Added client-side routing support for the SPA with paths (e.g. `/api`) or query-strings (e.g. `?content=api`). Configured via `.app.routing:String` option. Set to `"path"` or `"query"`. Uses page.js internally.
    + Implemented `EventEmitter`.
    + _BREAKING CHANGE_: Dropped `docma.ready()` method. Use `docma.on('ready', listener)` that's only triggered once on every page load or `docma.on('render', listener)` triggered when each content is rendered. Also see `docma.on('route', listener)` triggered when SPA route is changed.
    + Docma web initializing errors are no longer passed to event listeners. They are now immediately thrown.
    + `docma.app:Object` and `docma.template.main:String` are exposed to the SPA.
    + The `docma` object accessible by the SPA is now `Object.freeze`d.
    + Fixed bookmark scrolling.
    + Added new methods to `docma.utils` such as `getCodeName(symbol)`, `getFullName(symbol)`, etc...
    + If `debug >= 3`, web app will also output logs.

- <p>**Default Template**:</p>
    + Better layout for HTML files converted from markdown.
    + Fixed documentation of `@property` JSDoc tags.
    + Updated default template structure.
    + More supported languages for syntax highlighting (Javascript, JSON, CSS, HTML, XML, CoffeeScript, TypeScript, Bash, HTTP, Markdown, Dust and YAML).
    + Auto-language detection is enabled for syntax highlighting.
    + Style tables in HTML generated from markdown.
    + Style code blocks in HTML generated from markdown.
    + Better font display for code and summary/descriptions.
    + Font size of sidebar items are auto-adjusted to fit the sidebar, if they exceed the width.
    + Fixed incorrect symbols sort issue when symbol(s) have aliases.
    + Improved various API documentation styles.

- <p>Other:</p>
    + Manage web-component dependency packages via Bower.
    + Updated project structure.
    + Various minor revisions and clean-up.
    + Improved Docma source code documentation.

---

#### **v0.5.4** Pre-Release (2016-05-22)

- `docma.template.json` is no more copied over to the output.
- Added default template option `badges:Boolean`.

---

#### **v0.5.3** Pre-Release (2016-05-22)

- Fixed docma-web file paths.

---

#### **v0.5.2** Pre-Release (2016-05-20)

- Updated default template.
- Updated dependencies.
- Clean-up.

---

#### **v0.5.0** Pre-Release (2016-05-11)

- Initial (pre) release.
- Parse JSDoc documentation.
- Created default template.

[marked]:https://github.com/chjj/marked
[docma-david]:https://david-dm.org/onury/docma
