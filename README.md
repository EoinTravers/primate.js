# Primate.js

> A prehensile wrapper for the [Gorilla.sc](https://gorilla.sc/) API.

`primate.js` is a simple JavaScript package
that makes building online experiments with Gorilla a little easier.

If your code is running on Gorilla,
`primate.js` is just a verbose wrapper to the Gorilla API itself.
For example `primate.ready(func)` calls `gorilla.ready(func)`,
but also prints useful output to the JavaScript console:
`> 🦍: Setting 'func()' to run once the page is ready.`

If your code is running outside of Gorilla,
`primate.js` provides alternative versions of the Gorilla API
that do the same thing.
For example, `primate.ready(func)` calls jQuery's `$(document).ready(func)`.
This means you can run the same code with and without Gorilla.

The main purpose is to allow you to develop and debug your experiment
outside of Gorilla using a code editor,
which is a much more pleasant experience.

See https://gorilla.sc/support/api/gorilla for documentation on the original API.
Differences between `gorilla` and `primate` are outlined below.

## Dependencies

`primate.js` depends on jQuery,
which is already included in all Gorilla experiments.

## Differences to Gorilla

### Logging

`primate.js` logs as much information to the JavaScript console as possible.

    🦍: When running on Gorilla, output is prefaced with a gorilla icon, like so.

<!-- Break -->

    🙉: When running elsewhere, output is prefaced with a monkey.


### `primate.finish()`

Calling `primate.finish()` without any arguments will raise
a pop-up window when running on Gorilla, and will redirect
to the next node on Gorilla. This is the default behaviour
of `gorilla.finish()`.

Calling `primate.finish('example.com')` will redirect the
participant to example.com if the experiment is running off
Gorilla, but will send them to the next node in Gorilla.

Calling `primate.finish('example.com', true)` will redirect
to example.com even if running on Gorilla. You probably
don't want to do this!
