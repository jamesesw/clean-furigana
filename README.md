# Clean Furigana (HTML Formatter)

This script automatically converts Japanese sentences containing **furigana** into a clean, copy-paste friendly HTML format. It supports both:

- `base[furigana]` syntax (e.g., `漢字[かんじ]`)
- `<ruby><rt>` syntax (e.g., `<ruby>漢<rt>かん</rt></ruby>`)

The output is styled using `span` elements with `data-furi` attributes, allowing full CSS control over layout and presentation.

## 💡 Features

- ✅ Converts bracket-based and `<ruby>` furigana
- ✅ Preserves custom HTML tags and styles (e.g., `.expression`)
- ✅ Removes unnecessary spaces between Japanese characters
- ✅ Maintains natural word spacing for romaji and special characters
- ✅ Handles multiple `.furigana-text` blocks on the same page
- ✅ Ensures the resulting text is copyable as a **single readable line**, even if visually broken into multiple lines

---

## 📦 Examples

### Input

```html
<span class="furigana-text">
  お<ruby>姉<rt>ねえ</rt></ruby>さんは 背[せ]が 高[たか]いですね。
</span>
```

### Output (automatically generated and replaced by the original)

```html
<span class="furigana-text">
  <span class="word" data-furi="ねえ">姉</span>さんは
  <span class="word" data-furi="せ">背</span>が
  <span class="word" data-furi="たか">高</span>いですね。
</span>
```

Feel free to wrap your text in any style, and it should preserve it on the final output, such as:

```html
<span class="furigana-container">
  <h1>お<ruby>姉<rt>ねえ</rt></ruby>さんは<ruby>背<rt>せ</rt></ruby>が<ruby>高<rt>たか</rt></ruby>いですね。</a1>
</span>
```

---

## 🎨 Styling (CSS Example)

```css
.word {
  position: relative;
  display: inline-block;
}

.word::before {
  content: attr(data-furi);
  position: absolute;
  top: -1.2em;
  font-size: 0.6em;
  white-space: nowrap;
  left: 50%;
  transform: translateX(-50%);
}
```

---

## 📜 License

This project is licensed under the [MIT License](TBA).  
You are free to **use**, **modify**, and **include** this script in personal or commercial projects. Contributions and adaptations are welcome!

---

## 🤝 Contributions

If you’ve made improvements or found bugs, feel free to submit a pull request or open an issue. Suggestions are always appreciated!
