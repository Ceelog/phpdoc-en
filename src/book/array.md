Arrays
======

**Table of Contents**

-   [Introduction](/intro/array.html)
-   [Installing/Configuring](/array/setup.html)
    -   [Requirements](/array/setup.html#Requirements)
    -   [Installation](/array/setup.html#Installation)
    -   [Runtime
        Configuration](/array/setup.html#Runtime%20Configuration)
    -   [Resource Types](/array/setup.html#Resource%20Types)
-   [Predefined Constants](/array/constants.html)
-   [Sorting Arrays](/array/sorting.html)
-   [Array Functions](/ref/array.html)
    -   [array\_change\_key\_case](/ref/array.html#array_change_key_case)
        — Changes the case of all keys in an array
    -   [array\_chunk](/ref/array.html#array_chunk) — Split an array
        into chunks
    -   [array\_column](/ref/array.html#array_column) — Return the
        values from a single column in the input array
    -   [array\_combine](/ref/array.html#array_combine) — Creates an
        array by using one array for keys and another for its values
    -   [array\_count\_values](/ref/array.html#array_count_values) —
        Counts all the values of an array
    -   [array\_diff\_assoc](/ref/array.html#array_diff_assoc) —
        Computes the difference of arrays with additional index check
    -   [array\_diff\_key](/ref/array.html#array_diff_key) — Computes
        the difference of arrays using keys for comparison
    -   [array\_diff\_uassoc](/ref/array.html#array_diff_uassoc) —
        Computes the difference of arrays with additional index check
        which is performed by a user supplied callback function
    -   [array\_diff\_ukey](/ref/array.html#array_diff_ukey) — Computes
        the difference of arrays using a callback function on the keys
        for comparison
    -   [array\_diff](/ref/array.html#array_diff) — Computes the
        difference of arrays
    -   [array\_fill\_keys](/ref/array.html#array_fill_keys) — Fill an
        array with values, specifying keys
    -   [array\_fill](/ref/array.html#array_fill) — Fill an array with
        values
    -   [array\_filter](/ref/array.html#array_filter) — Filters elements
        of an array using a callback function
    -   [array\_flip](/ref/array.html#array_flip) — Exchanges all keys
        with their associated values in an array
    -   [array\_intersect\_assoc](/ref/array.html#array_intersect_assoc)
        — Computes the intersection of arrays with additional index
        check
    -   [array\_intersect\_key](/ref/array.html#array_intersect_key) —
        Computes the intersection of arrays using keys for comparison
    -   [array\_intersect\_uassoc](/ref/array.html#array_intersect_uassoc)
        — Computes the intersection of arrays with additional index
        check, compares indexes by a callback function
    -   [array\_intersect\_ukey](/ref/array.html#array_intersect_ukey) —
        Computes the intersection of arrays using a callback function on
        the keys for comparison
    -   [array\_intersect](/ref/array.html#array_intersect) — Computes
        the intersection of arrays
    -   [array\_key\_exists](/ref/array.html#array_key_exists) — Checks
        if the given key or index exists in the array
    -   [array\_key\_first](/ref/array.html#array_key_first) — Gets the
        first key of an array
    -   [array\_key\_last](/ref/array.html#array_key_last) — Gets the
        last key of an array
    -   [array\_keys](/ref/array.html#array_keys) — Return all the keys
        or a subset of the keys of an array
    -   [array\_map](/ref/array.html#array_map) — Applies the callback
        to the elements of the given arrays
    -   [array\_merge\_recursive](/ref/array.html#array_merge_recursive)
        — Merge one or more arrays recursively
    -   [array\_merge](/ref/array.html#array_merge) — Merge one or more
        arrays
    -   [array\_multisort](/ref/array.html#array_multisort) — Sort
        multiple or multi-dimensional arrays
    -   [array\_pad](/ref/array.html#array_pad) — Pad array to the
        specified length with a value
    -   [array\_pop](/ref/array.html#array_pop) — Pop the element off
        the end of array
    -   [array\_product](/ref/array.html#array_product) — Calculate the
        product of values in an array
    -   [array\_push](/ref/array.html#array_push) — Push one or more
        elements onto the end of array
    -   [array\_rand](/ref/array.html#array_rand) — Pick one or more
        random keys out of an array
    -   [array\_reduce](/ref/array.html#array_reduce) — Iteratively
        reduce the array to a single value using a callback function
    -   [array\_replace\_recursive](/ref/array.html#array_replace_recursive)
        — Replaces elements from passed arrays into the first array
        recursively
    -   [array\_replace](/ref/array.html#array_replace) — Replaces
        elements from passed arrays into the first array
    -   [array\_reverse](/ref/array.html#array_reverse) — Return an
        array with elements in reverse order
    -   [array\_search](/ref/array.html#array_search) — Searches the
        array for a given value and returns the first corresponding key
        if successful
    -   [array\_shift](/ref/array.html#array_shift) — Shift an element
        off the beginning of array
    -   [array\_slice](/ref/array.html#array_slice) — Extract a slice of
        the array
    -   [array\_splice](/ref/array.html#array_splice) — Remove a portion
        of the array and replace it with something else
    -   [array\_sum](/ref/array.html#array_sum) — Calculate the sum of
        values in an array
    -   [array\_udiff\_assoc](/ref/array.html#array_udiff_assoc) —
        Computes the difference of arrays with additional index check,
        compares data by a callback function
    -   [array\_udiff\_uassoc](/ref/array.html#array_udiff_uassoc) —
        Computes the difference of arrays with additional index check,
        compares data and indexes by a callback function
    -   [array\_udiff](/ref/array.html#array_udiff) — Computes the
        difference of arrays by using a callback function for data
        comparison
    -   [array\_uintersect\_assoc](/ref/array.html#array_uintersect_assoc)
        — Computes the intersection of arrays with additional index
        check, compares data by a callback function
    -   [array\_uintersect\_uassoc](/ref/array.html#array_uintersect_uassoc)
        — Computes the intersection of arrays with additional index
        check, compares data and indexes by separate callback functions
    -   [array\_uintersect](/ref/array.html#array_uintersect) — Computes
        the intersection of arrays, compares data by a callback function
    -   [array\_unique](/ref/array.html#array_unique) — Removes
        duplicate values from an array
    -   [array\_unshift](/ref/array.html#array_unshift) — Prepend one or
        more elements to the beginning of an array
    -   [array\_values](/ref/array.html#array_values) — Return all the
        values of an array
    -   [array\_walk\_recursive](/ref/array.html#array_walk_recursive) —
        Apply a user function recursively to every member of an array
    -   [array\_walk](/ref/array.html#array_walk) — Apply a user
        supplied function to every member of an array
    -   [array](/ref/array.html#array) — Create an array
    -   [arsort](/ref/array.html#arsort) — Sort an array in reverse
        order and maintain index association
    -   [asort](/ref/array.html#asort) — Sort an array and maintain
        index association
    -   [compact](/ref/array.html#compact) — Create array containing
        variables and their values
    -   [count](/ref/array.html#count) — Count all elements in an array,
        or something in an object
    -   [current](/ref/array.html#current) — Return the current element
        in an array
    -   [each](/ref/array.html#each) — Return the current key and value
        pair from an array and advance the array cursor
    -   [end](/ref/array.html#end) — Set the internal pointer of an
        array to its last element
    -   [extract](/ref/array.html#extract) — Import variables into the
        current symbol table from an array
    -   [in\_array](/ref/array.html#in_array) — Checks if a value exists
        in an array
    -   [key\_exists](/ref/array.html#key_exists) — Alias of
        array\_key\_exists
    -   [key](/ref/array.html#key) — Fetch a key from an array
    -   [krsort](/ref/array.html#krsort) — Sort an array by key in
        reverse order
    -   [ksort](/ref/array.html#ksort) — Sort an array by key
    -   [list](/ref/array.html#list) — Assign variables as if they were
        an array
    -   [natcasesort](/ref/array.html#natcasesort) — Sort an array using
        a case insensitive "natural order" algorithm
    -   [natsort](/ref/array.html#natsort) — Sort an array using a
        "natural order" algorithm
    -   [next](/ref/array.html#next) — Advance the internal pointer of
        an array
    -   [pos](/ref/array.html#pos) — Alias of current
    -   [prev](/ref/array.html#prev) — Rewind the internal array pointer
    -   [range](/ref/array.html#range) — Create an array containing a
        range of elements
    -   [reset](/ref/array.html#reset) — Set the internal pointer of an
        array to its first element
    -   [rsort](/ref/array.html#rsort) — Sort an array in reverse order
    -   [shuffle](/ref/array.html#shuffle) — Shuffle an array
    -   [sizeof](/ref/array.html#sizeof) — Alias of count
    -   [sort](/ref/array.html#sort) — Sort an array
    -   [uasort](/ref/array.html#uasort) — Sort an array with a
        user-defined comparison function and maintain index association
    -   [uksort](/ref/array.html#uksort) — Sort an array by keys using a
        user-defined comparison function
    -   [usort](/ref/array.html#usort) — Sort an array by values using a
        user-defined comparison function
