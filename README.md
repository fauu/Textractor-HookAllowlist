# Textractor-HookAllowlist

[Textractor] `texthook.dll` modification that allows blocking unnecessary
hooks. By default, the functionality is unchanged. But if there is an
`AllowedHooks.txt` file in the directory of the game’s executable file, only
hooks with names matching those listed in that file are allowed to be inserted.

## How to use

1. Install the regular Textractor version.

1. Download this repository’s [release archive][releases]. It contains 32- and
   64-bit versions of the modified `texthook.dll` file.

1. Replace the appropriate original `texthook.dll` in the regular Textraction
   installation directory with the appropriate modified `texthook.dll` file
   from the extracted release archive.

1. Launch Textractor along with your game.

1. Attach Textractor to the game.

1. Add custom hooks if necessary.

1. Verify whether the text is extracted.

1. Click “Save hook(s)” to make Textractor remember the game along with any
   custom hooks.

1. Note the *names* of the hooks you want to keep. The names are specified in
   the top dropdown.

    For example, [on this screenshot][names-ss], the name of the hook is
    `GetGlyphOutlineW`.

1. Create `AllowedHooks.txt` in the same directory as the game’s exe file and
   place the hook names in that file.

    The names should be in a single line, and they should **all** be terminated
    with a <kbd>TAB</kbd> character (copy it from here: `	`; text editors
    sometimes just insert spaces when <kbd>TAB</kbd> is pressed).

    > Examples:
    >
    > - I want to only allow hooks named `UserHook1`:
    >
    > ```txt
    > UserHook1[TAB]
    > ```
    >
    > - I want to only allow hooks named `KiriKiri1` or `KiriKiri2`:
    >
    > ```txt
    > KiriKiri1[TAB]KiriKiri2[TAB]
    > ```

    > [!WARNING]
    > If you are hooking a Unity game, you will need to allow the `Mono Searcher`
    > hook alongside your target hooks. Otherwise your target hooks will not be
    > inserted.

1. Close Textractor and the game, and reopen them.

Only hooks with the listed names should be inserted now. If you wish to allow
all hooks again, simply remove the file, or just rename it.

[Textractor]: https://github.com/Artikash/Textractor
[releases]: https://github.com/fauu/Textractor-HookAllowlist/releases/
[names-ss]: https://i.imgur.com/UHQvR35.png
