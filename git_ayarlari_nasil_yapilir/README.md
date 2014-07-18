# Git ayarları nasıl yapılır?

Git ayarları `~/.gitconfig` dosyasında tutuluyor. Bir projeye başlamadan önce bunların doğru ayarlandığına emin olun. Aksi takdirde commitlerinizde sizin bilgileriniz doğru bir şekilde yer almaz.

```
[color]
	ui = true
[user]
	name = Onur Ozgur OZKAN
	email = onur.ozgur.ozkan@lab2023.com
[core]
	editor = vim
	whitespace = fix,-indent-with-non-tab,trailing-space,cr-at-eol
	excludesfile = ~/.gitignore
[web]
	browser = google-chrome
```

* oh-my-zsh'ın [git eklentisini](https://github.com/robbyrussell/oh-my-zsh/blob/master/plugins/git/git.plugin.zsh) ve Vim'in [fugitive](https://github.com/tpope/vim-fugitive) eklentisini kullandığımızdan alias atamanıza gerek yoktur.
* Genel olarak ayarlarınız için mutlaka bir [dotfiles](https://github.com/onurozgurozkan/dotfiles) projeniz olsun. Ayarlarınızı bu projede tutun.

**Kaynaklar**

* http://git-scm.com/book/tr/Customizing-Git-Git-Configuration
