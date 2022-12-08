The "modal mode", which may be familiar to vim users, changes a little the way you interact with broot:

-   The input at the bottom isn't immediately focused, you must type a space, a `:`, or a `/` to focus it. And you unfocus it with the escape key.
-   The upside is you can use keyboard shortcuts without ctrl, for example you may move the selection with j and k.
-   The downside is you have one letter more to type to start searching, which isn't to dismiss as searching is usually the first thing you do in broot.

I recommand you **don't** activate this mode until you really tried broot. Broot isn't a text editor and can't be confused with one. This mode may be more comfortable when you constantly jump from vim to broot but only after you understood how broot works.

You may be an avid vim user, as I am, and still prefer not to use modality in broot. Starting in _command_ mode means you have one more letter to type before searching, because search is done in _input_ mode. And broot is search oriented and often used in very short sessions (less than 5 seconds from intent to launch to being back in the shell in the right directory or editing the right file in your favorite editor).

You need first to enable the "modal mode" with this line in the configuration:

HjsonTOML

```
modal: true
```

If `modal` isn't set to `true`, the single letter shortcuts you define in configuration will be ignored (so you don't have to remove them if you don't want modality anymore).

Broot may be in one of two modes:

1.  **input** mode, with the input field at the bottom focused and received standard keys
2.  **command** mode, with input not focused, and single key shortcuts enabled

In _command_ mode, you'll find those keys already configured: _`j` and `k` to go down and up_ `h` and `l` to go to parent or to enter a directory

You enter _input_ mode by typing one of those letters: (space), `:`, or `/`. You leave it with the `escape` key. You may add other bindings to the `:mode_input` and `:mode_command` verbs.