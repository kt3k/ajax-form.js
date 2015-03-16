# ajax-form.js v0.1.2

> Automatic `<form>` element which creates an ajax request according to the state of the inputs.
> You don't need to write any JavaScript just for wiring your forms and apis.

***Note:*** This lib depends on jQuery and qwest.

# Install

```sh
bower install --save ajax-form.js
```


# The markup

```html

<form class="ajax-form">

  <input name="user">

  <input name="comment">

  <button
    data-api="/api/comments"
    data-method="PUT">Send</button>

</form>
```

This form creates `PUT` request to `/api/comments` with data `user=[user]` and `comment=[comment]` when the button is pushed. (events are automatically bound)

## success / failure handling

```html

<form class="ajax-form" id="my-form">

    ...
    ...

</form>


<script>

$(function () {

    $('#my-form').on('success.ajax-form', function () {

        // some success handling

    }).on('failure.ajax-form', function () {

        // some failure handling

    });

});

</script>
```


## Manual initialization

`.ajax-form` elements are automatically initialized at `$(document).ready`. If you want to create `.ajax-form` elements after that, you can intialize them manually by triggering `init.ajax-form` event on `document` object.

```js

createFormAsync().then(function () {

    $(document).trigger('init.ajax-form');

});

```



# Similar projects

- https://github.com/incraigulous/jquery-ajax-form
- https://github.com/rnicholus/ajax-form
