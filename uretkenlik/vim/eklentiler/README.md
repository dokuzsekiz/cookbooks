# Eklentiler

## Vundle.vim

Vim için eklenti yönetimi eklentisidir. Vim'in bundlerı olarak düşünebiliriz.

1. `~/.vimrc` dosyasımızı vundle ile ilgili satırları ekledikten sonra `Plugin 'githubusername/githubrepo' şeklinde vim eklentilerimizi ekliyoruz.

```
" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim    " required
call vundle#begin()                  " required

Plugin 'gmarik/Vundle.vim'
Plugin 'tpope/vim-fugitive'          " <= Plugins are here

" All of your Plugins must be added before the following line
call vundle#end()                    " required
filetype plugin indent on            " required
```

2. Vim'i çalıştırdıktan sonra `:PluginInstall` komutunu koşun veya direk terminalden `vim +PluginInstall +qall` komutunu çalıştırabilirsiniz.

**Kaynaklar**

* https://github.com/gmarik/Vundle.vim#quick-start
