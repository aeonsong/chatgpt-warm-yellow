# ChatGPT Warm Yellow

A warm, low-glare UserStyle for ChatGPT Web with a cream-yellow Light Mode and a warm-charcoal Dark Mode.

The goal is simple: make long ChatGPT sessions feel visually quieter without flattening the interface or sacrificing contrast. Instead of tinting the whole UI yellow, the theme uses layered cream surfaces, restrained amber accents, and dedicated code surfaces.

## Highlights

- Warm cream Light Mode built around `#FDF6E3`
- Unified sidebar tone based on `#F8F0D9`
- Warm-charcoal Dark Mode instead of forcing Light Mode at night
- Amber accent color (`#D97706`) for primary actions and focus states
- Reworked code cards: outer shell, toolbar, body, copy controls, borders, and syntax colors
- Softer modal, menu, composer, hover, scrollbar, and selection colors
- Cleaner active/disabled button states with no harsh native black buttons
- Separate Light and Dark palettes that preserve ChatGPT's own Appearance switching
- Designed for Stylus/UserStyle use on `chatgpt.com`

## Install

1. Install a UserStyle manager such as [Stylus](https://github.com/openstyles/stylus).
2. Open [`chatgpt-warm-yellow.user.css`](./chatgpt-warm-yellow.user.css).
3. Copy the stylesheet into a new style for `chatgpt.com`, or use your UserStyle manager's install flow if it recognizes `.user.css` files.
4. Keep using ChatGPT's own **Light / Dark / System** appearance setting.

## Palette

| UI layer | Light Mode |
| --- | --- |
| Main canvas | `#FDF6E3` |
| Sidebar | `#F8F0D9` |
| Elevated surface | `#FEFBF3` |
| Hover / secondary surface | `#F3EADF` |
| Code body | `#F6ECD0` |
| Code toolbar | `#F2E6C7` |
| Accent | `#D97706` |
| Main text | `#4F4A45` |

Dark Mode uses the same hierarchy with warm charcoal and brown-black surfaces instead of neutral grey-black.

## What is customized

- Main conversation canvas
- Sidebar and active/hover states
- Composer/input area
- Primary, secondary, and disabled buttons
- Menus and popovers
- Settings/modals
- Chat/Work selector
- Suggested actions
- Code block shell, toolbar, body, copy controls, and syntax highlighting
- Tables
- Scrollbars
- Footer fades
- Temporary Chat controls
- Selection and focus states

## Code block treatment

ChatGPT currently uses multiple nested surfaces for code cards. This theme normalizes them into one coherent component with:

- a single rounded outer shell
- warm toolbar surface
- slightly different warm code body
- subtle border
- transparent copy controls with restrained hover feedback
- dedicated syntax colors for Light and Dark modes

This avoids the common mismatch where the code body is themed but the toolbar or copy gutter remains grey.

## Compatibility

Target: `https://chatgpt.com`

The theme relies on a mix of ChatGPT design tokens and structural selectors. ChatGPT changes its frontend frequently, so occasional maintenance may be required when components or class structures change.

If a future UI update introduces an unthemed grey/black surface, please open an issue with a screenshot, the affected component, Light/Dark mode, and browser + Stylus version when relevant.

## Notes

- This is an unofficial community UserStyle and is not affiliated with or endorsed by OpenAI.
- The theme changes presentation only; it does not change ChatGPT functionality.
- Warm colors may feel more comfortable to some users, but this project makes no medical claim about eye protection or eye strain.

## License

MIT
