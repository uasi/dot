# AGENTS.md

## Tool preference definition

```scheme
;; (prefer <prefered> <fallback>...)

(prefer ; tools
  specified-in-prompt
  project-defined
  (if javascript
    (prefer '(pnpm pnpr pnpx) '(npm npr npx))
  (if python
    (prefer uv "uv pip" pip))
  (if uncertain (ask))))

(prefer ; installer
  mise-project-local
  mise-global
  system-package-manager
  always-ask: '("curl | sh" manual-download))
```
