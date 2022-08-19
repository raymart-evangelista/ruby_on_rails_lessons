- What is the purpose of Turbo Drive?
  - Turbo Drive is part of Turbo which is a framework under the umbrella term Hotwire
  - Turbo Drive accelerates overall page navigation--watches when a user clicks a link, submits a form, handles request being made by user, and updates the page without a full reload

- How does Turbo Drive handle page navigation? What are the two kinds of page visit types in Turbo?
  - Application visit
    - Advance: default action and will result in a new entry being added to the browser history
    - Replace: replaces the most recent browser history entry with the new location
      - use attribute inside of Rails link tag to change to replace
  - Restoration visit
    - when user navigates using browser's forward and back buttons
    - if possible, Turbo Drive uses browser's cache to render a preview of page immediately, otherwise, will retrieve a fresh copy of the page over the network
    - the browser's scroll position is saved on every page before navigating away and will return to this saved position
    - Used by Turbo Drive internally so annotation is not needed for restoration

- How can you disable Turbo Drive?
  - when you want a full page reset
  - add `data-turbo="false"` directly on links or on parent containing them

- What is Turbolinks?
  - no longer in active development
  - Turbolinks goal was to capture request for any  clicked links in a web app, and if that link was to another page that wasn't an outside resource, Turbolinks keeps the current page instance alive and swaps out the content between the <body> tags of the document--meaning it was fast and a full page reload wasn't required
  - Turbolinks is the predecessor of Turbo