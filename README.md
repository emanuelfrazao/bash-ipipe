<h1>
bash interactive pipe
</h1>

---

**contents**

- [goal](#goal)
- [functional spec](#functional-spec)

# goal
make an interactive bash process that allows the user to experiment operations on stdin.

# functional spec

* the user flow will go something like:
    1. the user runs the module `ipipe` with whatever stdin, either directly, or piped into it 
    2. the module has no options;
    3. the module creates a sub-process in the same console;
    4. the user can then run any command on the sub-process, which:
       * receives as stdin the original stdin,
       * outputs to stdout in sub-process,
       * stays active, and goes to stage 4.;
    
* further requiring that:
    * every environment variable on the parent process should be available within the module's sub-process;
    * if the user presses Ctrl+A, the stdout of the next command will be redirected to all further ones;
    * if the user presses Ctrl+B, it undoes the previous Ctrl+A command;
    * the user must be able to redirect to a file



