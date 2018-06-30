# audit-rebuild-ama
Identifying ways to improve the accessibility, performance, and SEO ranking of AMA's website using web standards and industry-recommended best practices

## Methodology

I audited [AMA's home page](https://ama.ab.ca/) using Google Chrome's "Audits" panel, [the aXe accessibility extension for Chrome](https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd), [WebAIM's WAVE Web Accessibility Evaluation Tool](https://wave.webaim.org/), [the HTML5 Outliner extension for Chrome](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo?hl=en), [Google's PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/), and [Think With Google's Test My Site](https://testmysite.thinkwithgoogle.com/).

I've summarized these analyses, along with proposed solutions, in the "Areas For Improvement" section below. Where relevant, I've included quotes from people in the industry to offer further explanation for the solutions I've proposed.

## Areas For Improvement

### 1. Accessibility

#### 1. Website Relies Entirely On Client-Side JavaScript To Display Content

##### Why This Is A Problem

* If JavaScript fails, or is not delivered to the client, the user gets nothing
* On low-powered devices, throttled connections, or for users using feature phones or proxy browsers, it takes more than 3s for the page to load. An initial load time of > 3s is correlated with a high bounce rate for users. For AMA members who need to quickly access your services online, possibly on low-quality 3G connections (for example, along the highway or in rural areas), that task might prove impossible

##### Possible Solution(s)

* Content could be rendered server-side using [Angular Universal](https://angular.io/guide/universal) or simply as HTML/ASPX
* Simple, static pages that don't require complex state management could be served as HTML/ASPX instead of being handled as Angular app views

##### What Others Are Saying

>Well built web apps should work for the majority of users in that market. If they are built for resilience, they can avoid users staring at a white screen for seconds on first load, rather than the basic content for the experience[.]
>
>-- Addy Osmani, Eng. Manager at Google working with Chrome & DevRel, _[Progressive Web Apps with React.js: Part 4 — Progressive Enhancement](https://medium.com/@addyosmani/progressive-web-apps-with-react-js-part-4-site-is-progressively-enhanced-b5ad7cf7a447)_

#### 2. Home page is not fully keyboard-accessible

##### Why This Is A Problem

* A number of users -- including those with temporary, situational, or permanent disabilities -- rely on a keyboard to browse and navigate through websites

##### Possible Solution(s)

* Ensure that all focusable elements have a focus style
* Ensure that buttons are <button>s. If custom elements must be used, ensure that they have a role of "button" and can be triggered using the return key and the space bar

### 2. Performance

#### 1. Home page is currently loading over 1.5 MB of external stylesheets


