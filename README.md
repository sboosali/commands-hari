# commands-hari

## Installation:

* install `stack` from
http://docs.haskellstack.org/en/stable/install_and_upgrade/#mac-os-x
* `git clone https://github.com/sboosali/commands-hari`
* `cd commands-hari`
* `stack build`
* `stack exec -- commands-hari-server`

## Usage:

Edit the grammars/actions, and reboot the server.

## Dependencies:

* `NSSpeechRecognizer`, a "command-and-control" grammar
(i.e. only matches a set of phrases).
* `commands-core` to easily define grammars, parse recognized sentences,
interpret them as actions, and execute those actions.

The grammars you define must be finite (i.e. no "zero-or-more" combinators, no
arbitrary dictation); It is then "undistributed" into a list of commands.

Unfortunately,
a command-and-control grammar can't be interleaved with dictation. Example, you
can't say "camel recognize speech" to insert "recognizeSpeech". You'd have to (1)
enable Siri (with its keyboard shortcut), then dictate,
then disable Siri (TODO must?); (2)
assuming you've set a mark, or that the most recent dictation is highlighted,
say "camel that", having defined the appropriate grammar and interpretation.
