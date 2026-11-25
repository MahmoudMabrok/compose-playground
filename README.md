# Compose Playground

Write Jetpack Compose in your browser and see it run live — an interactive preview powered by Kotlin/Wasm.

**[Open the playground](https://mo3ta.top/compose-playground/)**

## Features

- **Kotlin editor in the browser.** Write Compose in a [CodeMirror](https://codemirror.net/) editor with Kotlin highlighting, line numbers, and Compose autocompletion.
- **Live preview on the real Compose runtime.** The preview is a Kotlin/Wasm app. Clicks, `remember` state, animations, effects, and coroutines run on Jetpack Compose itself — not a mock.
- **Edits without a reload.** Typing is debounced and sent to the preview in place, so the composition stays up and remembered state survives your next edit.
- **Errors on the exact line.** Parse and runtime errors are highlighted on the editor line they came from, and they also appear in the console.
- **Share links.** Share copies a link with your code compressed into the URL hash (`#zcode=`), along with preview mode, entry name, and theme. Anyone who opens it gets your snippet already loaded and running. No account required.
- **Built-in examples.** Start from **Counter** (button clicks and remembered state), **List** (a scrolling list you can add to), or **Animation** (`animateDpAsState` / `animateColorAsState`).
- **Content and Previews modes.** Content mode fills the preview with your entry composable (default: `App`). Previews mode renders every `@Preview` in the snippet.
- **Light and dark themes.** Switch in the toolbar, or let the playground follow your system preference. The last session is saved in the browser when the URL has no share hash.

Keyboard shortcuts: <kbd>Ctrl</kbd>/<kbd>Cmd</kbd>+<kbd>S</kbd> copies a share link, <kbd>Ctrl</kbd>/<kbd>Cmd</kbd>+<kbd>Enter</kbd> runs again, and <kbd>Ctrl</kbd>/<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd> drops remembered state and runs again.

## How it works

The shell is a TypeScript page with the CodeMirror editor. The preview is a small Kotlin/Wasm host that interprets your source with [Fast Compose](https://github.com/fast-compose) on the real Compose runtime. There is no compile server: edits update the running composition in the browser.

Fast Compose covers a subset of Compose APIs. Unknown calls become stand-ins and show up as warnings. There is no type checker.

## Browser requirements

The preview needs [WebAssembly garbage collection](https://kotlinlang.org/docs/wasm-configuration.html). Use a recent browser:

- Chrome 119 or later
- Edge 119 or later
- Firefox 120 or later
- Safari 18.2 or later (including Safari on iOS / iPadOS 18.2+)

## Credits

The preview is powered by the [Fast Compose](https://github.com/fast-compose) engine by [Ma7moud3ly](https://github.com/Ma7moud3ly), licensed under [Apache License 2.0](https://github.com/fast-compose/fast-compose/blob/main/LICENSE).

## Feedback

Ideas, bugs, and questions are welcome in [Issues](https://github.com/MahmoudMabrok/compose-playground/issues).

## Author

Built by [Mahmoud Mabrok](https://github.com/MahmoudMabrok).

## License

[Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
