Semaphore, Shared Memory and IPC
================================

**Table of Contents**

-   [Introduction](/intro/sem.html)
-   [Installing/Configuring](/sem/setup.html)
    -   [Requirements](/sem/setup.html#Requirements)
    -   [Installation](/sem/setup.html#Installation)
    -   [Runtime Configuration](/sem/setup.html#Runtime%20Configuration)
    -   [Resource Types](/sem/setup.html#Resource%20Types)
-   [Predefined Constants](/sem/constants.html)
-   [Semaphore Functions](/ref/sem.html)
    -   [ftok](/ref/sem.html#ftok) — Convert a pathname and a project
        identifier to a System V IPC key
    -   [msg\_get\_queue](/ref/sem.html#msg_get_queue) — Create or
        attach to a message queue
    -   [msg\_queue\_exists](/ref/sem.html#msg_queue_exists) — Check
        whether a message queue exists
    -   [msg\_receive](/ref/sem.html#msg_receive) — Receive a message
        from a message queue
    -   [msg\_remove\_queue](/ref/sem.html#msg_remove_queue) — Destroy a
        message queue
    -   [msg\_send](/ref/sem.html#msg_send) — Send a message to a
        message queue
    -   [msg\_set\_queue](/ref/sem.html#msg_set_queue) — Set information
        in the message queue data structure
    -   [msg\_stat\_queue](/ref/sem.html#msg_stat_queue) — Returns
        information from the message queue data structure
    -   [sem\_acquire](/ref/sem.html#sem_acquire) — Acquire a semaphore
    -   [sem\_get](/ref/sem.html#sem_get) — Get a semaphore id
    -   [sem\_release](/ref/sem.html#sem_release) — Release a semaphore
    -   [sem\_remove](/ref/sem.html#sem_remove) — Remove a semaphore
    -   [shm\_attach](/ref/sem.html#shm_attach) — Creates or open a
        shared memory segment
    -   [shm\_detach](/ref/sem.html#shm_detach) — Disconnects from
        shared memory segment
    -   [shm\_get\_var](/ref/sem.html#shm_get_var) — Returns a variable
        from shared memory
    -   [shm\_has\_var](/ref/sem.html#shm_has_var) — Check whether a
        specific entry exists
    -   [shm\_put\_var](/ref/sem.html#shm_put_var) — Inserts or updates
        a variable in shared memory
    -   [shm\_remove\_var](/ref/sem.html#shm_remove_var) — Removes a
        variable from shared memory
    -   [shm\_remove](/ref/sem.html#shm_remove) — Removes shared memory
        from Unix systems
