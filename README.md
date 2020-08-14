# compilerun

Quickly compile a source file and run that program.

```terminal
$ compilerun gcc c calculator -- 1 + 2
g++ (GCC) 8.3.1 20190223 (Red Hat 8.3.1-2)
+ gcc -o calculator calculator.c
+ ./calculator 1 + 2
3
```

Features:
- Tab-completion friendly: auto-detect source file from executable name

Developed as a productivity aid, `compilerun` is intended to be used via shell
aliases or functions.
By convention, the alias or function name is the compiler name with suffix `r`.

Examples:
```bash
alias gccr='compilerun gcc c'
alias g++r='compilerun g++ cpp,cc'

gxxr() {
    local source="$1"
    shift 1
    compilerun g++ cpp,cc "$source" -std=gnu++17 -g -O2 $@
}
```
