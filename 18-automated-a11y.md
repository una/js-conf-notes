30 Minutes or Less: The Magic of Automated Accessibility Testing by [Marcy Sutton](http://twitter.com/marcysutton)
---

> Pizza is always the answer

### Things you should focus on:

- alternative text
- document hierarchy & structure
- HTML semantics
- color contrast
- keyboard interactivity
- focus management

> *nothing replaces real user feedback*

### Manual Testing

1. Tab through the page w/a keyboard to check focus states (i.e. gov.uk)
2. Demo on a screen reader (demo: Soundcloud)

### Sorta-Automated Testing

1. Headings & Semantic Structure: [Firefox Web Developer Toolbar](https://addons.mozilla.org/en-us/firefox/addon/web-developer/)
2. Overall Page A11y: [Chrome Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) (Canary has a dev tools experiment)
3. The Accessibility Tree (concept): `chrome://accessibility/`
4. [A11y](https://github.com/addyosmani/a11y) CLI by Addy Osmani: `npm install --global a11y` --> there's also a grunt task (uses Phantom)


### Definitely Automated Testing

- [Protractor](https://docs.angularjs.org/guide/e2e-testing): end-to-end testing for Angular -- test for focus management, color contrast etc.
- write tests, then run protractor in command line
- uses Selenium
- ngAria for Angular accessibility

- conduct user evaluations
- learn about ARIA
- check out the [slide resources](https://github.com/angular/material-start)
