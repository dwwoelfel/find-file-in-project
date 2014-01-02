find-file-in-project that uses git ls-files instead of find.

You'll probably also want to do something like:

```
(global-set-key (kbd "C-x f") 'find-file-in-project)

(setq ffip-patterns '("html" "org" "txt" "md" "el" "clj" "hamlc" "less" "coffee"
                      "py" "rb" "js" "pl" "sh" "erl" "hs" "ml"))

(setq ffip-project-root-function (lambda ()
                                   (replace-regexp-in-string "\n$" ""
                                                             (shell-command-to-string "git rev-parse --show-toplevel"))))

(setq ffip-limit 100000)
```
