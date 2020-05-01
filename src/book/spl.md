Standard PHP Library (SPL)
==========================

**Table of Contents**

-   [Introduction](/intro/spl.html)
-   [Installing/Configuring](/spl/setup.html)
    -   [Requirements](/spl/setup.html#Requirements)
    -   [Installation](/spl/setup.html#Installation)
    -   [Runtime Configuration](/spl/setup.html#Runtime%20Configuration)
    -   [Resource Types](/spl/setup.html#Resource%20Types)
-   [Predefined Constants](/spl/constants.html)
-   [Datastructures](/spl/datastructures.html)
    -   [SplDoublyLinkedList](/spl/datastructures.html#SplDoublyLinkedList)
        — The SplDoublyLinkedList class
    -   [SplStack](/spl/datastructures.html#SplStack) — The SplStack
        class
    -   [SplQueue](/spl/datastructures.html#SplQueue) — The SplQueue
        class
    -   [SplHeap](/spl/datastructures.html#SplHeap) — The SplHeap class
    -   [SplMaxHeap](/spl/datastructures.html#SplMaxHeap) — The
        SplMaxHeap class
    -   [SplMinHeap](/spl/datastructures.html#SplMinHeap) — The
        SplMinHeap class
    -   [SplPriorityQueue](/spl/datastructures.html#SplPriorityQueue) —
        The SplPriorityQueue class
    -   [SplFixedArray](/spl/datastructures.html#SplFixedArray) — The
        SplFixedArray class
    -   [SplObjectStorage](/spl/datastructures.html#SplObjectStorage) —
        The SplObjectStorage class
-   [Iterators](/spl/iterators.html)
    -   [AppendIterator](/spl/iterators.html#AppendIterator) — The
        AppendIterator class
    -   [ArrayIterator](/spl/iterators.html#ArrayIterator) — The
        ArrayIterator class
    -   [CachingIterator](/spl/iterators.html#CachingIterator) — The
        CachingIterator class
    -   [CallbackFilterIterator](/spl/iterators.html#CallbackFilterIterator)
        — The CallbackFilterIterator class
    -   [DirectoryIterator](/spl/iterators.html#DirectoryIterator) — The
        DirectoryIterator class
    -   [EmptyIterator](/spl/iterators.html#EmptyIterator) — The
        EmptyIterator class
    -   [FilesystemIterator](/spl/iterators.html#FilesystemIterator) —
        The FilesystemIterator class
    -   [FilterIterator](/spl/iterators.html#FilterIterator) — The
        FilterIterator class
    -   [GlobIterator](/spl/iterators.html#GlobIterator) — The
        GlobIterator class
    -   [InfiniteIterator](/spl/iterators.html#InfiniteIterator) — The
        InfiniteIterator class
    -   [IteratorIterator](/spl/iterators.html#IteratorIterator) — The
        IteratorIterator class
    -   [LimitIterator](/spl/iterators.html#LimitIterator) — The
        LimitIterator class
    -   [MultipleIterator](/spl/iterators.html#MultipleIterator) — The
        MultipleIterator class
    -   [NoRewindIterator](/spl/iterators.html#NoRewindIterator) — The
        NoRewindIterator class
    -   [ParentIterator](/spl/iterators.html#ParentIterator) — The
        ParentIterator class
    -   [RecursiveArrayIterator](/spl/iterators.html#RecursiveArrayIterator)
        — The RecursiveArrayIterator class
    -   [RecursiveCachingIterator](/spl/iterators.html#RecursiveCachingIterator)
        — The RecursiveCachingIterator class
    -   [RecursiveCallbackFilterIterator](/spl/iterators.html#RecursiveCallbackFilterIterator)
        — The RecursiveCallbackFilterIterator class
    -   [RecursiveDirectoryIterator](/spl/iterators.html#RecursiveDirectoryIterator)
        — The RecursiveDirectoryIterator class
    -   [RecursiveFilterIterator](/spl/iterators.html#RecursiveFilterIterator)
        — The RecursiveFilterIterator class
    -   [RecursiveIteratorIterator](/spl/iterators.html#RecursiveIteratorIterator)
        — The RecursiveIteratorIterator class
    -   [RecursiveRegexIterator](/spl/iterators.html#RecursiveRegexIterator)
        — The RecursiveRegexIterator class
    -   [RecursiveTreeIterator](/spl/iterators.html#RecursiveTreeIterator)
        — The RecursiveTreeIterator class
    -   [RegexIterator](/spl/iterators.html#RegexIterator) — The
        RegexIterator class
-   [Interfaces](/spl/interfaces.html)
    -   [Countable](/spl/interfaces.html#Countable) — The Countable
        interface
    -   [OuterIterator](/spl/interfaces.html#OuterIterator) — The
        OuterIterator interface
    -   [RecursiveIterator](/spl/interfaces.html#RecursiveIterator) —
        The RecursiveIterator interface
    -   [SeekableIterator](/spl/interfaces.html#SeekableIterator) — The
        SeekableIterator interface
-   [Exceptions](/spl/exceptions.html)
    -   [BadFunctionCallException](/spl/exceptions.html#BadFunctionCallException)
        — The BadFunctionCallException class
    -   [BadMethodCallException](/spl/exceptions.html#BadMethodCallException)
        — The BadMethodCallException class
    -   [DomainException](/spl/exceptions.html#DomainException) — The
        DomainException class
    -   [InvalidArgumentException](/spl/exceptions.html#InvalidArgumentException)
        — The InvalidArgumentException class
    -   [LengthException](/spl/exceptions.html#LengthException) — The
        LengthException class
    -   [LogicException](/spl/exceptions.html#LogicException) — The
        LogicException class
    -   [OutOfBoundsException](/spl/exceptions.html#OutOfBoundsException)
        — The OutOfBoundsException class
    -   [OutOfRangeException](/spl/exceptions.html#OutOfRangeException)
        — The OutOfRangeException class
    -   [OverflowException](/spl/exceptions.html#OverflowException) —
        The OverflowException class
    -   [RangeException](/spl/exceptions.html#RangeException) — The
        RangeException class
    -   [RuntimeException](/spl/exceptions.html#RuntimeException) — The
        RuntimeException class
    -   [UnderflowException](/spl/exceptions.html#UnderflowException) —
        The UnderflowException class
    -   [UnexpectedValueException](/spl/exceptions.html#UnexpectedValueException)
        — The UnexpectedValueException class
-   [SPL Functions](/ref/spl.html)
    -   [class\_implements](/ref/spl.html#class_implements) — Return the
        interfaces which are implemented by the given class or interface
    -   [class\_parents](/ref/spl.html#class_parents) — Return the
        parent classes of the given class
    -   [class\_uses](/ref/spl.html#class_uses) — Return the traits used
        by the given class
    -   [iterator\_apply](/ref/spl.html#iterator_apply) — Call a
        function for every element in an iterator
    -   [iterator\_count](/ref/spl.html#iterator_count) — Count the
        elements in an iterator
    -   [iterator\_to\_array](/ref/spl.html#iterator_to_array) — Copy
        the iterator into an array
    -   [spl\_autoload\_call](/ref/spl.html#spl_autoload_call) — Try all
        registered \_\_autoload() functions to load the requested class
    -   [spl\_autoload\_extensions](/ref/spl.html#spl_autoload_extensions)
        — Register and return default file extensions for spl\_autoload
    -   [spl\_autoload\_functions](/ref/spl.html#spl_autoload_functions)
        — Return all registered \_\_autoload() functions
    -   [spl\_autoload\_register](/ref/spl.html#spl_autoload_register) —
        Register given function as \_\_autoload() implementation
    -   [spl\_autoload\_unregister](/ref/spl.html#spl_autoload_unregister)
        — Unregister given function as \_\_autoload() implementation
    -   [spl\_autoload](/ref/spl.html#spl_autoload) — Default
        implementation for \_\_autoload()
    -   [spl\_classes](/ref/spl.html#spl_classes) — Return available SPL
        classes
    -   [spl\_object\_hash](/ref/spl.html#spl_object_hash) — Return hash
        id for given object
    -   [spl\_object\_id](/ref/spl.html#spl_object_id) — Return the
        integer object handle for given object
-   [File Handling](/spl/files.html)
    -   [SplFileInfo](/spl/files.html#SplFileInfo) — The SplFileInfo
        class
    -   [SplFileObject](/spl/files.html#SplFileObject) — The
        SplFileObject class
    -   [SplTempFileObject](/spl/files.html#SplTempFileObject) — The
        SplTempFileObject class
-   [Miscellaneous Classes and Interfaces](/spl/misc.html)
    -   [ArrayObject](/spl/misc.html#ArrayObject) — The ArrayObject
        class
    -   [SplObserver](/spl/misc.html#SplObserver) — The SplObserver
        interface
    -   [SplSubject](/spl/misc.html#SplSubject) — The SplSubject
        interface
