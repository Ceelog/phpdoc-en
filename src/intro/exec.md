Those functions provide means to execute commands on the system itself,
and means to secure such commands.

> **Note**:
>
> All execution functions call the commands through *cmd.exe* under
> Windows. Therefore the user calling these functions needs appropriate
> privilege to run this command. The only exception is <span
> class="function">proc\_open</span> with *bypass\_shell* option.
