# HTML General

## Forms

```html
<form class="form" action="/register" method="POST">
  <div class="form-group mb-2">
    <label for="email">Email address</label>
    <input class="form-control" type="text" name="email" placeholder="Enter email" style="width: 300px; margin: 0px 50px 25px 0px">
    <label for="password">Password</label>
    <input class="form-control" type="text" name="password" placeholder="Password" style="width: 300px; margin: 0px 50px 25px 0px">
    <button type="submit" class="btn btn-primary">Register</button>
  </div>
</form>
```

The `method` and `action` detail what happens to the inputed values of the form when the `button` is pressed.

The `name` variable links an `input` to a `label`.

The `type` variable signifies what the input field should expect, and adjusts functionality accordingly.
* `password` hides the characters as they are entered

If `required` is added to the end of an `input` field, a pop-up tells the user it needs to be filled out if the `button` is pressed.

