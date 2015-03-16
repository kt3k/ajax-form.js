# ajax-form.js v0.1.1

> Automatic `<form>` element which creates a ajax request according to the state of the inputs.
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

    $('my-form').on('success.ajax-form', function () {

        // some success handling

    });

    $('my-form').on('failure.ajax-form', function () {

        // some failure handling

    });

});

</script>
```


# Similar projects

- https://github.com/incraigulous/jquery-ajax-form
- https://github.com/rnicholus/ajax-form
