Layer 설정
============
<pre>
  <code>
   dotspacemacs-configuration-layers
   '(
     ;; ----------------------------------------------------------------
     ;; Example of useful layers you may want to use right away.
     ;; Uncomment some layer names and press <SPC f e R> (Vim style) or
     ;; <M-m f e R> (Emacs style) to install them.
     ;; ----------------------------------------------------------------
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
  </code>
</pre>

PHP 설정
=============


Scroll 설정
=============
<pre>
  <code>
  dotspacemacs-smooth-scrolling ni
  dotspacemacs-additional-packages '(sublimity)
  
  (require 'sublimity)
  (require 'sublimity-scroll)
  ;; (require 'sublimity-map)
  (require 'sublimity-attractive)
  
  </code>
</pre>
