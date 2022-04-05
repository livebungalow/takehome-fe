# Feedback

## Thoughts

* Vuetify is very useful. I'm not an CSS expert but can make a page look good enough.

## Assumptions

* We only have a few properties. (Pagination isn't implemented yet.) I afraid that 100 properties in
  a given market will crash the browser.

## Nice-to-have

* It'd be nice to know if the individual fields about a property are compulsory or not. For instance,
  a property with some rooms available but the prices are not listed.
* Each market's listing should have its own route instead of forcing the users to select from the list of
  markets. (Examples: `/austin`, `/baltimore`)

## Not implemented

* Pagination
* Tests
* Error handling. (Example: What if the REST API endpoints are down?)
* Consideration for mobile
* Searching for a specific property