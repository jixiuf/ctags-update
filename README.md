[![MELPA](http://melpa.org/packages/ctags-update-badge.svg)](http://melpa.org/#/ctags-update)


The easiest way to get started is to install the package via [MELPA][melpa]:

 [melpa]: http://melpa.org/

```elisp
(package-install 'ctags-update)
```

(auto) update TAGS using exuberant-ctags


     (ctags-global-auto-update-mode)
     (setq ctags-update-prompt-create-tags nil);you need manually create TAGS in your project 
     
     ;; or only turn it on for some special mode

    (autoload 'turn-on-ctags-auto-update-mode "ctags-update" "turn on 'ctags-auto-update-mode'." t)
    (add-hook 'c-mode-common-hook  'turn-on-ctags-auto-update-mode)
     ...
    (add-hook 'emacs-lisp-mode-hook  'turn-on-ctags-auto-update-mode)




    ;if you want to update (create) TAGS manually
    (autoload 'ctags-update "ctags-update" "update TAGS using ctags" t)
    (global-set-key "\C-cE" 'ctags-update)
    
with prefix 'C-u' ,then you can generate a new TAGS file in your selected directory,
with prefix 'C-uC-u' same to prefix 'C-u',but save it to kill-ring instead of execute it."


when you save a file ,`ctags-auto-update-mode` will update TAGS using `exuberant-ctags`.

custom the interval  of updating TAGS  by `ctags-update-delay-seconds` .



on windows ,you can custom `ctags-update-command` like this:

    (when (equal system-type 'windows-nt)
      (setq ctags-update-command (expand-file-name  "~/.emacs.d/bin/ctags.exe")))
