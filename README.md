# Markdown Unicode Headers

A Vim plugin that displays markdown headers with Unicode double-struck or fullwidth characters.

## Features

- Configurable font styles (double-struck or fullwidth) per header level
- Optional all-caps transformation per header level
- Uses Vim's native conceal feature
- Yank copies the original text (works with clipboard or [OSC52](https://github.com/ojroques/vim-oscyank))
- Cut and Paste or screenshot from the terminal will capture the Unicode titles

Screenshot using [Solarized8](https://github.com/lifepillar/vim-solarized8) and [Jetbrains Mono](https://www.jetbrains.com/lp/mono/)

![Screenshot](https://github.com/user-attachments/assets/3f6cf6a0-5ce6-4744-bc50-f21f2eeaafd9)


## Installation

### vim-plug
```vim
Plug 'Voltron369/markdown-headers.vim'
```

### Vundle
```vim
Plugin 'Voltron369/markdown-headers.vim'
```

### Pathogen
```bash
cd ~/.vim/bundle
git clone https://github.com/Voltron369/markdown-headers.vim.git
```

## Configuration

Add to your `.vimrc`:

```vim
" Font style: 'doublestruck' or 'fullwidth'
let g:md_h1_style = 'doublestruck'
let g:md_h2_style = 'doublestruck'
" ... h3-h6

" All caps: 1 = enabled, 0 = disabled
let g:md_h1_caps = 1
let g:md_h2_caps = 0
" ... h3-h6

" Optional: Add commands to toggle styles
command! MarkdownHeadersToggle call s:ToggleHeaders()

function! s:ToggleHeaders()
  if &conceallevel == 0
    setlocal conceallevel=2
  else
    setlocal conceallevel=0
  endif
endfunction
```

## Defaults

- H1: ＦＵＬＬＷＩＤＴＨ，　ＡＬＬ　ＣＡＰＳ
- H2: Ｆｕｌｌｗｉｄｔｈ，　ｎｏｒｍａｌ　ｃａｓｅ
- H3: 𝔻𝕆𝕌𝔹𝕃𝔼𝕊𝕋ℝ𝕌ℂ𝕂, 𝔸𝕃𝕃 ℂ𝔸ℙ𝕊
- H4: 𝔻𝕠𝕦𝕓𝕝𝕖𝕤𝕥𝕣𝕦𝕔𝕜, 𝕟𝕠𝕣𝕞𝕒𝕝 𝕔𝕒𝕤𝕖
- H5: NORMAL FONT, ALL CAPS
- H6: Normal font, normal case

## Requirements

- Vim 7.3+ with conceal support
- Terminal/font with Unicode support
