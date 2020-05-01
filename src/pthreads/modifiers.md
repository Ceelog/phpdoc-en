Method Modifiers
================

**Warning**

These semantics are only applicable to pthreads v2 - they have been
removed in pthreads v3.

pthreads overrides the functionality of the protected and private method
modifiers in order to provide functionality more suited to
multi-threaded objects. pthreads applies this functionality to all
Threaded objects from creation.

**Example \#1 protected method example: protected methods can only be
executed by one Thread at a time.**

``` php
<?php
class ExampleThread extends Thread {
    public function run() {
        /* thread code */
        if ($this->synchronized()) {

        }
    }

    protected function exclusive() {
        /* synchronized method */
    }
}

$thread = new ExampleThread();
if ($thread->start()) {
    $thread->exclusive();
}
?>
```

**Example \#2 private method example: private methods may only be
executed by the Threaded object during execution**

``` php
<?php
class ExampleThread extends Thread {
    public function run() {
        /* thread code */
        if ($this->insideonly()) {

        }
    }

    private function insideonly() {
        /* private method */
    }
}

$thread = new ExampleThread();
if ($thread->start()) {
    $thread->insideonly();
}
?>
```
