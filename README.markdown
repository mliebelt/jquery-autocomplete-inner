# Example for using autocomplete inside textareas

This project provides mainly examples how to use the JQuery autocomplete UI so that the
user is able to complete a substring inside a textarea or textfield.

It works like this:

1. Define which regexpression should match the substring inside the editor.
2. Define the result set that has to be filtered.
3. Call the JavaScript function provided with the following information:
   * ID of your widget
   * regexpression you have defined
   * result set as defined in [Autocomplete Demo][http://jqueryui.com/demos/autocomplete/]

As a result, your user may type any text. If the regexpression matches the text before the cursor
position, the drop down list pop ups if the substring matches some of the values in the result set.
By selecting some result, that result is inserted instead of the matched substring, and the cursor
stays at that position.

## Starting the examples

Use the following examples:

1. cities-local.html: Standalone version that should work offline.
2. citites.html: Same version, but resources are taken from the internet

The difference here is only, that cities-local.html does not need anything from the internet,
citites.html needs the connection to get jquery and jquery-ui from the internet.

To start the example, just open the page `cities-local.html` or `cities.html` in any browser, and type in the name of cities mixed with any text. The cities are held in a variable in `application.js`, and could be replaced by any other content locally or remote. See the options for that at [jquery autocomplete](http://jqueryui.com/demos/autocomplete/).

## Implementation

Base for the implementation was the answer of [abstraktor on stackoverflow](http://stackoverflow.com/questions/1781927/is-it-possible-to-get-autocomplete-for-a-rails-application-in-text-editors-not-o)
to my question about using jquery autocomplete inside a textarea. Based on that code,
I added the following things:

1. Use the word matching the giving regexpression in front of the cursor.
2. Insert the selected matching string for the substring.
3. Find a functioning implementation of positioning the cursor inside a textarea or textfield
   (see the [question on stackoverflow](http://stackoverflow.com/questions/499126/jquery-set-cursor-position-in-text-area)
   with the implementation there)

The implementation is contained only in the file application.js, the rest is taken from jquery only.
