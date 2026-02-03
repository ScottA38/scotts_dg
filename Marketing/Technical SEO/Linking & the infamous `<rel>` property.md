
## Attributes
### `nofollow`
Tell Web Scrapers not to index the URL specified specified in the link

### `noopener`
Navigate to the target resource without granting access to the document that opened it.

##### Cases
- `noopener` **not specified** - [`Window.opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener)browser property passed to the new Web Page (hypertext document)
- `rel=noopener` **specified** - [`Window.opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener)not passed to the new Web Page and new browsing context cannot access any information about the previous page in JavaScript