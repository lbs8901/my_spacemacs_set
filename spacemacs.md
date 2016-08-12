Layer 설정
============
<pre>
 dotspacemacs-configuration-layers
 '(
   auto-completion
   better-defaults
   emacs-lisp
   osx
   php
   git
   markdown
   org
   javascript
   html
   sql
   gtags
   (shell :variables
          shell-default-height 30
          shell-default-position 'bottom)
   spell-checking
   syntax-checking
   version-control
   )
</pre>


Scroll 설정
=============
<pre>
* basic config
dotspacemacs-smooth-scrolling ni
dotspacemacs-additional-packages '(sublimity)

* dotspacemacs/user-config
(require 'sublimity)
(require 'sublimity-scroll)
;; (require 'sublimity-map)
;; (require 'sublimity-attractive)
(sublimity-mode t)

* bottom
(setq scroll-step           1
    scroll-conservatively 10000)
</pre>

기타 설정
=============

<pre>
;;disable backup
(setq backup-inhibited t)
(setq make-backup-files nil)
;;disable auto save
(setq auto-save-default nil)

;; back tab func
(defun un-indent-by-removing-4-spaces ()
  "remove 4 spaces from beginning of of line"
  (interactive)
  (save-excursion
    (save-match-data
      (beginning-of-line)
      ;; get rid of tabs at beginning of line
      (when (looking-at "^\\s-+")
        (untabify (match-beginning 0) (match-end 0)))
      (when (looking-at "^    ")
        (replace-match "")))))
        
;; word-wrap
(setq-default truncate-lines t)
;; set font
(set-default-font "Bitstream Vera Sans Mono 15")

;; tab to stop
(custom-set-variables
 ;; custom-set-variables was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right.
 '(tab-stop-list
   (quote
    (4 8 12 16 20 24 28 32 36 40 44 48 52 56 60 64 68 72 76 80 84 88 92 96 100 104 108 112 116 120)))
 )

;; redisplay
(setq redisplay-dont-pause t)

;; s-left, s-right
(global-set-key (kbd "<s-left>") 'beginning-of-line-text)
(global-set-key (kbd "<s-right>") 'end-of-line)
</pre>

PHP 설정
=============
