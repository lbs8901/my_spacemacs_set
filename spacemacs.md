Layer 설정
============
<pre>
  <code>
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
  </code>
</pre>

PHP 설정
=============


Scroll 설정
=============
<pre>
  <code>
  
  * basic config
  dotspacemacs-smooth-scrolling ni
  dotspacemacs-additional-packages '(sublimity)
  
  * dotspacemacs/user-init
  (require 'sublimity)
  (require 'sublimity-scroll)
  ;; (require 'sublimity-map)
  ;; (require 'sublimity-attractive)
  
  * bottom
  (setq scroll-step           1
      scroll-conservatively 10000)

  
  </code>
</pre>
