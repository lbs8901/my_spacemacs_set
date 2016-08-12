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

* bottom
(setq scroll-step           1
    scroll-conservatively 10000)
</pre>

sublimity 설정
=============
<pre>
dotspacemacs-additional-packages '(sublimity)

* dotspacemacs/user-config
(require 'sublimity)
(require 'sublimity-scroll)
;; (require 'sublimity-map)
;; (require 'sublimity-attractive)
(sublimity-mode t)
</pre>

기타 설정
=============

<pre>

;; backup, auto save disable
(setq make-backup-files nil)
(setq auto-save-default nil)
(setq create-lockfiles nil)

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

</pre>

hot-key 설정
=============
<pre>
;; s-left, s-right
(define-key global-map (kbd "s-<left>")     'beginning-of-line-text)
(define-key global-map (kbd "s-<right>")    'end-of-line)
(define-key global-map (kbd "s-<up>")       'scroll-down)
(define-key global-map (kbd "s-<down>")     'scroll-up)

(defun custom-indent-newline ()
  (interactive)
  (default-indent-new-line)
  (indent-relative)
  )

;; RET indent
(define-key global-map (kbd "RET") 'default-indent-new-line)
(define-key global-map (kbd "<C-return>") 'custom-indent-newline)

;; search set
(define-key global-map (kbd "C-F") 'helm-projectile-ag)
(global-set-key (kbd "C-x C-f") 'helm-for-files)
(define-key global-map (kbd "C-,") 'helm-projectile)

;; duplicate line
(defun duplicate-current-line-or-region (arg)
  "Duplicates the current line or region ARG times.
If there's no region, the current line will be duplicated. However, if
there's a region, all lines that region covers will be duplicated."
  (interactive "p")
  (let (beg end (origin (point)))
    (if (and mark-active (> (point) (mark)))
        (exchange-point-and-mark))
    (setq beg (line-beginning-position))
    (if mark-active
        (exchange-point-and-mark))
    (setq end (line-end-position))
    (let ((region (buffer-substring-no-properties beg end)))
      (dotimes (i arg)
        (goto-char end)
        (newline)
        (insert region)
        (setq end (point)))
      (goto-char (+ origin (* (length region) arg) arg)))))

(global-set-key (kbd "s-d") 'duplicate-current-line-or-region)

</pre>

additional package 설정
=============
* sx : Stack Exchange for Emacs


PHP 설정
=============
