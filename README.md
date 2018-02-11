# urxv-buffer2vim

This project provides a urxvt extension to open the current buffer in vim. (I'm sure it can easily be adapted to use emacs or other editors).  
It was inspired by [reactivity](https://github.com/jeromebelleman/reactivity) vim part.  

Once triggered, urxvt will create a temp file or a pipe and launch a new urxvt client with vim. After that, the terminal continues available.  

## Getting Started

1. Copy the `buffer2vim` perl script in `~/.urxvt/ext`  
2. Enable it in `.Xresources`:
   ```
   URxvt.perl-ext-common:      ...,buffer2vim
   URxvt.keysym.C-s:           perl:buffer2vim:vim_last
   URxvt.keysym.C-S:           perl:buffer2vim:vim
   urxvt.buffer2vim.lastrows:  3000
   ```
   and reload the file:
   `$ [[ -f ~/.Xresources ]] && xrdb -merge -I$HOME ~/.Xresources`
3. Launch `$ urxvt`

## Configuration

The configuration is done through `.Xresources`, it supports the following keys:
```
! Number of rows to show with vim_last, default 1024:
urxvt.buffer2vim.lastrows: POSITIVE INT
! If you want to use temp files or a pipe to feed vim, default 'file':
urxvt.buffer2vim.tmpfiletype: 'file' | 'pipe'
```
With the configuration from the previous section you can use Ctrl+S to show only the last 3000 lines in VIM or Ctrl+Shift+S to show the whole buffer.  

## Authors

* **Jose M Perez Ramos** - [Kuroneer](https://github.com/Kuroneer)

## License

This project is released under the MIT License. Check [LICENSE](LICENSE) for more information.

