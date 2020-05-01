Examples
========

**Example \#1 Examples of valid patterns**

-   <span class="simpara">*/\<\\/\\w+\>/*</span>
-   <span class="simpara">*\|(\\d{3})-\\d+\|Sm*</span>
-   <span class="simpara">*/^(?i)php\[34\]/*</span>
-   <span class="simpara">*{^\\s+(\\s+)?$}*</span>

**Example \#2 Examples of invalid patterns**

-   <span class="simpara"> */href='(.\*)'* - missing ending delimiter
    </span>
-   <span class="simpara"> */\\w+\\s\*\\w+/J* - unknown modifier 'J'
    </span>
-   <span class="simpara"> *1-\\d3-\\d3-\\d4\|* - missing starting
    delimiter </span>
