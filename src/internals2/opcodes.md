Zend Engine 2 Opcodes
=====================

**Table of Contents**

-   [Opcode Descriptions and Examples](/internals2/opcodes/list.html)
    -   [ADD](/internals2/opcodes/add.html)
    -   [ADD\_ARRAY\_ELEMENT](/internals2/opcodes/add-array-element.html)
    -   [ADD\_CHAR](/internals2/opcodes/add-char.html)
    -   [ADD\_INTERFACE](/internals2/opcodes/add-interface.html)
    -   [ADD\_STRING](/internals2/opcodes/add-string.html)
    -   [ADD\_VAR](/internals2/opcodes/add-var.html)
    -   [ASSIGN](/internals2/opcodes/assign.html)
    -   [ASSIGN\_ADD](/internals2/opcodes/assign-add.html)
    -   [ASSIGN\_BW\_AND](/internals2/opcodes/assign-bw-and.html)
    -   [ASSIGN\_BW\_OR](/internals2/opcodes/assign-bw-or.html)
    -   [ASSIGN\_BW\_XOR](/internals2/opcodes/assign-bw-xor.html)
    -   [ASSIGN\_CONCAT](/internals2/opcodes/assign-concat.html)
    -   [ASSIGN\_DIM](/internals2/opcodes/assign-dim.html)
    -   [ASSIGN\_DIV](/internals2/opcodes/assign-div.html)
    -   [ASSIGN\_MOD](/internals2/opcodes/assign-mod.html)
    -   [ASSIGN\_MUL](/internals2/opcodes/assign-mul.html)
    -   [ASSIGN\_OBJ](/internals2/opcodes/assign-obj.html)
    -   [ASSIGN\_REF](/internals2/opcodes/assign-ref.html)
    -   [ASSIGN\_SL](/internals2/opcodes/assign-sl.html)
    -   [ASSIGN\_SR](/internals2/opcodes/assign-sr.html)
    -   [ASSIGN\_SUB](/internals2/opcodes/assign-sub.html)
    -   [BEGIN\_SILENCE](/internals2/opcodes/begin-silence.html)
    -   [BOOL](/internals2/opcodes/bool.html)
    -   [BOOL\_NOT](/internals2/opcodes/bool-not.html)
    -   [BOOL\_XOR](/internals2/opcodes/bool-xor.html)
    -   [BRK](/internals2/opcodes/brk.html)
    -   [BW\_AND](/internals2/opcodes/bw-and.html)
    -   [BW\_NOT](/internals2/opcodes/bw-not.html)
    -   [BW\_OR](/internals2/opcodes/bw-or.html)
    -   [BW\_XOR](/internals2/opcodes/bw-xor.html)
    -   [CASE](/internals2/opcodes/case.html)
    -   [CAST](/internals2/opcodes/cast.html)
    -   [CATCH](/internals2/opcodes/catch.html)
    -   [CLONE](/internals2/opcodes/clone.html)
    -   [CONCAT](/internals2/opcodes/concat.html)
    -   [CONT](/internals2/opcodes/cont.html)
    -   [DECLARE\_CLASS](/internals2/opcodes/declare-class.html)
    -   [DECLARE\_CONST](/internals2/opcodes/declare-const.html)
    -   [DECLARE\_FUNCTION](/internals2/opcodes/declare-function.html)
    -   [DECLARE\_INHERITED\_CLASS](/internals2/opcodes/declare-inherited-class.html)
    -   [DECLARE\_INHERITED\_CLASS\_DELAYED](/internals2/opcodes/declare-inherited-class-delayed.html)
    -   [DIV](/internals2/opcodes/div.html)
    -   [DO\_FCALL](/internals2/opcodes/do-fcall.html)
    -   [DO\_FCALL\_BY\_NAME](/internals2/opcodes/do-fcall-by-name.html)
    -   [ECHO](/internals2/opcodes/echo.html)
    -   [END\_SILENCE](/internals2/opcodes/end-silence.html)
    -   [EXIT](/internals2/opcodes/exit.html)
    -   [EXT\_FCALL\_BEGIN](/internals2/opcodes/ext-fcall-begin.html)
    -   [EXT\_FCALL\_END](/internals2/opcodes/ext-fcall-end.html)
    -   [EXT\_NOP](/internals2/opcodes/ext-nop.html)
    -   [EXT\_STMT](/internals2/opcodes/ext-stmt.html)
    -   [FE\_FETCH](/internals2/opcodes/fe-fetch.html)
    -   [FE\_RESET](/internals2/opcodes/fe-reset.html)
    -   [FETCH\_CLASS](/internals2/opcodes/fetch-class.html)
    -   [FETCH\_CONSTANT](/internals2/opcodes/fetch-constant.html)
    -   [FETCH\_DIM\_FUNC\_ARG](/internals2/opcodes/fetch-dim-func-arg.html)
    -   [FETCH\_DIM\_IS](/internals2/opcodes/fetch-dim-is.html)
    -   [FETCH\_DIM\_R](/internals2/opcodes/fetch-dim-r.html)
    -   [FETCH\_DIM\_RW](/internals2/opcodes/fetch-dim-rw.html)
    -   [FETCH\_DIM\_TMP\_VAR](/internals2/opcodes/fetch-dim-tmp-var.html)
    -   [FETCH\_DIM\_UNSET](/internals2/opcodes/fetch-dim-unset.html)
    -   [FETCH\_DIM\_W](/internals2/opcodes/fetch-dim-w.html)
    -   [FETCH\_FUNC\_ARG](/internals2/opcodes/fetch-func-arg.html)
    -   [FETCH\_IS](/internals2/opcodes/fetch-is.html)
    -   [FETCH\_OBJ\_FUNC\_ARG](/internals2/opcodes/fetch-obj-func-arg.html)
    -   [FETCH\_OBJ\_IS](/internals2/opcodes/fetch-obj-is.html)
    -   [FETCH\_OBJ\_R](/internals2/opcodes/fetch-obj-r.html)
    -   [FETCH\_OBJ\_RW](/internals2/opcodes/fetch-obj-rw.html)
    -   [FETCH\_OBJ\_UNSET](/internals2/opcodes/fetch-obj-unset.html)
    -   [FETCH\_OBJ\_W](/internals2/opcodes/fetch-obj-w.html)
    -   [FETCH\_R](/internals2/opcodes/fetch-r.html)
    -   [FETCH\_RW](/internals2/opcodes/fetch-rw.html)
    -   [FETCH\_UNSET](/internals2/opcodes/fetch-unset.html)
    -   [FETCH\_W](/internals2/opcodes/fetch-w.html)
    -   [FREE](/internals2/opcodes/free.html)
    -   [GOTO](/internals2/opcodes/goto.html)
    -   [HANDLE\_EXCEPTION](/internals2/opcodes/handle-exception.html)
    -   [INCLUDE\_OR\_EVAL](/internals2/opcodes/include-or-eval.html)
    -   [INIT\_ARRAY](/internals2/opcodes/init-array.html)
    -   [INIT\_FCALL\_BY\_NAME](/internals2/opcodes/init-fcall-by-name.html)
    -   [INIT\_METHOD\_CALL](/internals2/opcodes/init-method-call.html)
    -   [INIT\_NS\_FCALL\_BY\_NAME](/internals2/opcodes/init-ns-fcall-by-name.html)
    -   [INIT\_STATIC\_METHOD\_CALL](/internals2/opcodes/init-static-method-call.html)
    -   [INIT\_STRING](/internals2/opcodes/init-string.html)
    -   [INSTANCEOF](/internals2/opcodes/instanceof.html)
    -   [IS\_EQUAL](/internals2/opcodes/is-equal.html)
    -   [IS\_IDENTICAL](/internals2/opcodes/is-identical.html)
    -   [IS\_NOT\_EQUAL](/internals2/opcodes/is-not-equal.html)
    -   [IS\_NOT\_IDENTICAL](/internals2/opcodes/is-not-identical.html)
    -   [IS\_SMALLER](/internals2/opcodes/is-smaller.html)
    -   [IS\_SMALLER\_OR\_EQUAL](/internals2/opcodes/is-smaller-or-equal.html)
    -   [ISSET\_ISEMPTY\_DIM\_OBJ](/internals2/opcodes/isset-isempty-dim-obj.html)
    -   [ISSET\_ISEMPTY\_PROP\_OBJ](/internals2/opcodes/isset-isempty-prop-obj.html)
    -   [ISSET\_ISEMPTY\_VAR](/internals2/opcodes/isset-isempty-var.html)
    -   [JMP](/internals2/opcodes/jmp.html)
    -   [JMPNZ](/internals2/opcodes/jmpnz.html)
    -   [JMPNZ\_EX](/internals2/opcodes/jmpnz-ex.html)
    -   [JMPZ](/internals2/opcodes/jmpz.html)
    -   [JMPZ\_EX](/internals2/opcodes/jmpz-ex.html)
    -   [JMPZNZ](/internals2/opcodes/jmpznz.html)
    -   [MOD](/internals2/opcodes/mod.html)
    -   [MUL](/internals2/opcodes/mul.html)
    -   [NEW](/internals2/opcodes/new.html)
    -   [NOP](/internals2/opcodes/nop.html)
    -   [POST\_DEC](/internals2/opcodes/post-dec.html)
    -   [POST\_DEC\_OBJ](/internals2/opcodes/post-dec-obj.html)
    -   [POST\_INC](/internals2/opcodes/post-inc.html)
    -   [POST\_INC\_OBJ](/internals2/opcodes/post-inc-obj.html)
    -   [PRE\_DEC](/internals2/opcodes/pre-dec.html)
    -   [PRE\_DEC\_OBJ](/internals2/opcodes/pre-dec-obj.html)
    -   [PRE\_INC](/internals2/opcodes/pre-inc.html)
    -   [PRE\_INC\_OBJ](/internals2/opcodes/pre-inc-obj.html)
    -   [PRINT](/internals2/opcodes/print.html)
    -   [QM\_ASSIGN](/internals2/opcodes/qm-assign.html)
    -   [RAISE\_ABSTRACT\_ERROR](/internals2/opcodes/raise-abstract-error.html)
    -   [RECV](/internals2/opcodes/recv.html)
    -   [RECV\_INIT](/internals2/opcodes/recv-init.html)
    -   [RETURN](/internals2/opcodes/return.html)
    -   [RETURN\_BY\_REF](/internals2/opcodes/return-by-ref.html)
    -   [SEND\_REF](/internals2/opcodes/send-ref.html)
    -   [SEND\_VAL](/internals2/opcodes/send-val.html)
    -   [SEND\_VAR](/internals2/opcodes/send-var.html)
    -   [SEND\_VAR\_NO\_REF](/internals2/opcodes/send-var-no-ref.html)
    -   [SL](/internals2/opcodes/sl.html)
    -   [SR](/internals2/opcodes/sr.html)
    -   [SUB](/internals2/opcodes/sub.html)
    -   [SWITCH\_FREE](/internals2/opcodes/switch-free.html)
    -   [THROW](/internals2/opcodes/throw.html)
    -   [TICKS](/internals2/opcodes/ticks.html)
    -   [UNSET\_DIM](/internals2/opcodes/unset-dim.html)
    -   [UNSET\_OBJ](/internals2/opcodes/unset-obj.html)
    -   [UNSET\_VAR](/internals2/opcodes/unset-var.html)
    -   [USER\_OPCODE](/internals2/opcodes/user-opcode.html)
    -   [VERIFY\_ABSTRACT\_CLASS](/internals2/opcodes/verify-abstract-class.html)
    -   [ZEND\_DECLARE\_LAMBDA\_FUNCTION](/internals2/opcodes/zend-declare-lambda-function.html)
    -   [ZEND\_JMP\_SET](/internals2/opcodes/zend-jmp-set.html)

When parsing PHP files, Zend Engine 2 generates a series of operation
codes, commonly known as "opcodes", representing the function of the
code. This part of the manual details those opcodes and their behaviour.

Opcodes may be dumped for a given PHP file using the vld extension (see
<a href="https://pecl.php.net/package/vld" class="link external">» https://pecl.php.net/package/vld</a>).

| Number | Name                                                                                                                | Has sample code? |
|--------|---------------------------------------------------------------------------------------------------------------------|------------------|
| 0      | <a href="/internals2/opcodes/nop.html" class="xref">NOP</a>                                                         | yes              |
| 1      | <a href="/internals2/opcodes/add.html" class="xref">ADD</a>                                                         | yes              |
| 2      | <a href="/internals2/opcodes/sub.html" class="xref">SUB</a>                                                         | yes              |
| 3      | <a href="/internals2/opcodes/mul.html" class="xref">MUL</a>                                                         | yes              |
| 4      | <a href="/internals2/opcodes/div.html" class="xref">DIV</a>                                                         | yes              |
| 5      | <a href="/internals2/opcodes/mod.html" class="xref">MOD</a>                                                         | yes              |
| 6      | <a href="/internals2/opcodes/sl.html" class="xref">SL</a>                                                           | yes              |
| 7      | <a href="/internals2/opcodes/sr.html" class="xref">SR</a>                                                           | yes              |
| 8      | <a href="/internals2/opcodes/concat.html" class="xref">CONCAT</a>                                                   | yes              |
| 9      | <a href="/internals2/opcodes/bw-or.html" class="xref">BW_OR</a>                                                     | yes              |
| 10     | <a href="/internals2/opcodes/bw-and.html" class="xref">BW_AND</a>                                                   | yes              |
| 11     | <a href="/internals2/opcodes/bw-xor.html" class="xref">BW_XOR</a>                                                   | yes              |
| 12     | <a href="/internals2/opcodes/bw-not.html" class="xref">BW_NOT</a>                                                   | yes              |
| 13     | <a href="/internals2/opcodes/bool-not.html" class="xref">BOOL_NOT</a>                                               | yes              |
| 14     | <a href="/internals2/opcodes/bool-xor.html" class="xref">BOOL_XOR</a>                                               | yes              |
| 15     | <a href="/internals2/opcodes/is-identical.html" class="xref">IS_IDENTICAL</a>                                       | yes              |
| 16     | <a href="/internals2/opcodes/is-not-identical.html" class="xref">IS_NOT_IDENTICAL</a>                               | yes              |
| 17     | <a href="/internals2/opcodes/is-equal.html" class="xref">IS_EQUAL</a>                                               | yes              |
| 18     | <a href="/internals2/opcodes/is-not-equal.html" class="xref">IS_NOT_EQUAL</a>                                       | yes              |
| 19     | <a href="/internals2/opcodes/is-smaller.html" class="xref">IS_SMALLER</a>                                           | yes              |
| 20     | <a href="/internals2/opcodes/is-smaller-or-equal.html" class="xref">IS_SMALLER_OR_EQUAL</a>                         | yes              |
| 21     | <a href="/internals2/opcodes/cast.html" class="xref">CAST</a>                                                       | yes              |
| 22     | <a href="/internals2/opcodes/qm-assign.html" class="xref">QM_ASSIGN</a>                                             | yes              |
| 23     | <a href="/internals2/opcodes/assign-add.html" class="xref">ASSIGN_ADD</a>                                           | yes              |
| 24     | <a href="/internals2/opcodes/assign-sub.html" class="xref">ASSIGN_SUB</a>                                           | yes              |
| 25     | <a href="/internals2/opcodes/assign-mul.html" class="xref">ASSIGN_MUL</a>                                           | yes              |
| 26     | <a href="/internals2/opcodes/assign-div.html" class="xref">ASSIGN_DIV</a>                                           | yes              |
| 27     | <a href="/internals2/opcodes/assign-mod.html" class="xref">ASSIGN_MOD</a>                                           | yes              |
| 28     | <a href="/internals2/opcodes/assign-sl.html" class="xref">ASSIGN_SL</a>                                             | yes              |
| 29     | <a href="/internals2/opcodes/assign-sr.html" class="xref">ASSIGN_SR</a>                                             | yes              |
| 30     | <a href="/internals2/opcodes/assign-concat.html" class="xref">ASSIGN_CONCAT</a>                                     | yes              |
| 31     | <a href="/internals2/opcodes/assign-bw-or.html" class="xref">ASSIGN_BW_OR</a>                                       | yes              |
| 32     | <a href="/internals2/opcodes/assign-bw-and.html" class="xref">ASSIGN_BW_AND</a>                                     | yes              |
| 33     | <a href="/internals2/opcodes/assign-bw-xor.html" class="xref">ASSIGN_BW_XOR</a>                                     | yes              |
| 34     | <a href="/internals2/opcodes/pre-inc.html" class="xref">PRE_INC</a>                                                 | yes              |
| 35     | <a href="/internals2/opcodes/pre-dec.html" class="xref">PRE_DEC</a>                                                 | yes              |
| 36     | <a href="/internals2/opcodes/post-inc.html" class="xref">POST_INC</a>                                               | yes              |
| 37     | <a href="/internals2/opcodes/post-dec.html" class="xref">POST_DEC</a>                                               | yes              |
| 38     | <a href="/internals2/opcodes/assign.html" class="xref">ASSIGN</a>                                                   | yes              |
| 39     | <a href="/internals2/opcodes/assign-ref.html" class="xref">ASSIGN_REF</a>                                           | yes              |
| 40     | <a href="/internals2/opcodes/echo.html" class="xref">ECHO</a>                                                       | yes              |
| 41     | <a href="/internals2/opcodes/print.html" class="xref">PRINT</a>                                                     | yes              |
| 42     | <a href="/internals2/opcodes/jmp.html" class="xref">JMP</a>                                                         | yes              |
| 43     | <a href="/internals2/opcodes/jmpz.html" class="xref">JMPZ</a>                                                       | yes              |
| 44     | <a href="/internals2/opcodes/jmpnz.html" class="xref">JMPNZ</a>                                                     | yes              |
| 45     | <a href="/internals2/opcodes/jmpznz.html" class="xref">JMPZNZ</a>                                                   | yes              |
| 46     | <a href="/internals2/opcodes/jmpz-ex.html" class="xref">JMPZ_EX</a>                                                 | yes              |
| 47     | <a href="/internals2/opcodes/jmpnz-ex.html" class="xref">JMPNZ_EX</a>                                               | yes              |
| 48     | <a href="/internals2/opcodes/case.html" class="xref">CASE</a>                                                       | yes              |
| 49     | <a href="/internals2/opcodes/switch-free.html" class="xref">SWITCH_FREE</a>                                         | yes              |
| 50     | <a href="/internals2/opcodes/brk.html" class="xref">BRK</a>                                                         | yes              |
| 51     | <a href="/internals2/opcodes/cont.html" class="xref">CONT</a>                                                       | yes              |
| 52     | <a href="/internals2/opcodes/bool.html" class="xref">BOOL</a>                                                       | yes              |
| 53     | <a href="/internals2/opcodes/init-string.html" class="xref">INIT_STRING</a>                                         | yes              |
| 54     | <a href="/internals2/opcodes/add-char.html" class="xref">ADD_CHAR</a>                                               | yes              |
| 55     | <a href="/internals2/opcodes/add-string.html" class="xref">ADD_STRING</a>                                           | yes              |
| 56     | <a href="/internals2/opcodes/add-var.html" class="xref">ADD_VAR</a>                                                 | yes              |
| 57     | <a href="/internals2/opcodes/begin-silence.html" class="xref">BEGIN_SILENCE</a>                                     | yes              |
| 58     | <a href="/internals2/opcodes/end-silence.html" class="xref">END_SILENCE</a>                                         | yes              |
| 59     | <a href="/internals2/opcodes/init-fcall-by-name.html" class="xref">INIT_FCALL_BY_NAME</a>                           | yes              |
| 60     | <a href="/internals2/opcodes/do-fcall.html" class="xref">DO_FCALL</a>                                               | yes              |
| 61     | <a href="/internals2/opcodes/do-fcall-by-name.html" class="xref">DO_FCALL_BY_NAME</a>                               | yes              |
| 62     | <a href="/internals2/opcodes/return.html" class="xref">RETURN</a>                                                   | yes              |
| 63     | <a href="/internals2/opcodes/recv.html" class="xref">RECV</a>                                                       | yes              |
| 64     | <a href="/internals2/opcodes/recv-init.html" class="xref">RECV_INIT</a>                                             | yes              |
| 65     | <a href="/internals2/opcodes/send-val.html" class="xref">SEND_VAL</a>                                               | yes              |
| 66     | <a href="/internals2/opcodes/send-var.html" class="xref">SEND_VAR</a>                                               | yes              |
| 67     | <a href="/internals2/opcodes/send-ref.html" class="xref">SEND_REF</a>                                               | yes              |
| 68     | <a href="/internals2/opcodes/new.html" class="xref">NEW</a>                                                         | yes              |
| 69     | <a href="/internals2/opcodes/init-ns-fcall-by-name.html" class="xref">INIT_NS_FCALL_BY_NAME</a>                     | no               |
| 70     | <a href="/internals2/opcodes/free.html" class="xref">FREE</a>                                                       | yes              |
| 71     | <a href="/internals2/opcodes/init-array.html" class="xref">INIT_ARRAY</a>                                           | yes              |
| 72     | <a href="/internals2/opcodes/add-array-element.html" class="xref">ADD_ARRAY_ELEMENT</a>                             | yes              |
| 73     | <a href="/internals2/opcodes/include-or-eval.html" class="xref">INCLUDE_OR_EVAL</a>                                 | yes              |
| 74     | <a href="/internals2/opcodes/unset-var.html" class="xref">UNSET_VAR</a>                                             | yes              |
| 75     | <a href="/internals2/opcodes/unset-dim.html" class="xref">UNSET_DIM</a>                                             | yes              |
| 76     | <a href="/internals2/opcodes/unset-obj.html" class="xref">UNSET_OBJ</a>                                             | yes              |
| 77     | <a href="/internals2/opcodes/fe-reset.html" class="xref">FE_RESET</a>                                               | yes              |
| 78     | <a href="/internals2/opcodes/fe-fetch.html" class="xref">FE_FETCH</a>                                               | yes              |
| 79     | <a href="/internals2/opcodes/exit.html" class="xref">EXIT</a>                                                       | yes              |
| 80     | <a href="/internals2/opcodes/fetch-r.html" class="xref">FETCH_R</a>                                                 | yes              |
| 81     | <a href="/internals2/opcodes/fetch-dim-r.html" class="xref">FETCH_DIM_R</a>                                         | yes              |
| 82     | <a href="/internals2/opcodes/fetch-obj-r.html" class="xref">FETCH_OBJ_R</a>                                         | yes              |
| 83     | <a href="/internals2/opcodes/fetch-w.html" class="xref">FETCH_W</a>                                                 | yes              |
| 84     | <a href="/internals2/opcodes/fetch-dim-w.html" class="xref">FETCH_DIM_W</a>                                         | yes              |
| 85     | <a href="/internals2/opcodes/fetch-obj-w.html" class="xref">FETCH_OBJ_W</a>                                         | yes              |
| 86     | <a href="/internals2/opcodes/fetch-rw.html" class="xref">FETCH_RW</a>                                               | yes              |
| 87     | <a href="/internals2/opcodes/fetch-dim-rw.html" class="xref">FETCH_DIM_RW</a>                                       | yes              |
| 88     | <a href="/internals2/opcodes/fetch-obj-rw.html" class="xref">FETCH_OBJ_RW</a>                                       | yes              |
| 89     | <a href="/internals2/opcodes/fetch-is.html" class="xref">FETCH_IS</a>                                               | yes              |
| 90     | <a href="/internals2/opcodes/fetch-dim-is.html" class="xref">FETCH_DIM_IS</a>                                       | no               |
| 91     | <a href="/internals2/opcodes/fetch-obj-is.html" class="xref">FETCH_OBJ_IS</a>                                       | no               |
| 92     | <a href="/internals2/opcodes/fetch-func-arg.html" class="xref">FETCH_FUNC_ARG</a>                                   | yes              |
| 93     | <a href="/internals2/opcodes/fetch-dim-func-arg.html" class="xref">FETCH_DIM_FUNC_ARG</a>                           | yes              |
| 94     | <a href="/internals2/opcodes/fetch-obj-func-arg.html" class="xref">FETCH_OBJ_FUNC_ARG</a>                           | yes              |
| 95     | <a href="/internals2/opcodes/fetch-unset.html" class="xref">FETCH_UNSET</a>                                         | no               |
| 96     | <a href="/internals2/opcodes/fetch-dim-unset.html" class="xref">FETCH_DIM_UNSET</a>                                 | no               |
| 97     | <a href="/internals2/opcodes/fetch-obj-unset.html" class="xref">FETCH_OBJ_UNSET</a>                                 | no               |
| 98     | <a href="/internals2/opcodes/fetch-dim-tmp-var.html" class="xref">FETCH_DIM_TMP_VAR</a>                             | yes              |
| 99     | <a href="/internals2/opcodes/fetch-constant.html" class="xref">FETCH_CONSTANT</a>                                   | yes              |
| 100    | <a href="/internals2/opcodes/goto.html" class="xref">GOTO</a>                                                       | no               |
| 101    | <a href="/internals2/opcodes/ext-stmt.html" class="xref">EXT_STMT</a>                                               | yes              |
| 102    | <a href="/internals2/opcodes/ext-fcall-begin.html" class="xref">EXT_FCALL_BEGIN</a>                                 | no               |
| 103    | <a href="/internals2/opcodes/ext-fcall-end.html" class="xref">EXT_FCALL_END</a>                                     | no               |
| 104    | <a href="/internals2/opcodes/ext-nop.html" class="xref">EXT_NOP</a>                                                 | no               |
| 105    | <a href="/internals2/opcodes/ticks.html" class="xref">TICKS</a>                                                     | yes              |
| 106    | <a href="/internals2/opcodes/send-var-no-ref.html" class="xref">SEND_VAR_NO_REF</a>                                 | no               |
| 107    | <a href="/internals2/opcodes/catch.html" class="xref">CATCH</a>                                                     | yes              |
| 108    | <a href="/internals2/opcodes/throw.html" class="xref">THROW</a>                                                     | yes              |
| 109    | <a href="/internals2/opcodes/fetch-class.html" class="xref">FETCH_CLASS</a>                                         | yes              |
| 110    | <a href="/internals2/opcodes/clone.html" class="xref">CLONE</a>                                                     | yes              |
| 111    | <a href="/internals2/opcodes/return-by-ref.html" class="xref">RETURN_BY_REF</a>                                     | no               |
| 112    | <a href="/internals2/opcodes/init-method-call.html" class="xref">INIT_METHOD_CALL</a>                               | yes              |
| 113    | <a href="/internals2/opcodes/init-static-method-call.html" class="xref">INIT_STATIC_METHOD_CALL</a>                 | yes              |
| 114    | <a href="/internals2/opcodes/isset-isempty-var.html" class="xref">ISSET_ISEMPTY_VAR</a>                             | yes              |
| 115    | <a href="/internals2/opcodes/isset-isempty-dim-obj.html" class="xref">ISSET_ISEMPTY_DIM_OBJ</a>                     | yes              |
| 116    | ZEND\_SEND\_VAL\_EX                                                                                                 | no               |
| 117    | ZEND\_SEND\_VAR                                                                                                     | no               |
| 118    | ZEND\_INIT\_USER\_CALL                                                                                              | no               |
| 119    | ZEND\_SEND\_ARRAY                                                                                                   | no               |
| 120    | ZEND\_SEND\_USER                                                                                                    | no               |
| 121    | ZEND\_STRLEN                                                                                                        | no               |
| 122    | ZEND\_DEFINED                                                                                                       | no               |
| 123    | ZEND\_TYPE\_CHECK                                                                                                   | no               |
| 124    | ZEND\_VERIFY\_RETURN\_TYPE                                                                                          | no               |
| 125    | ZEND\_FE\_RESET\_RW                                                                                                 | no               |
| 126    | ZEND\_FE\_FETCH\_RW                                                                                                 | no               |
| 127    | ZEND\_FE\_FREE                                                                                                      | no               |
| 128    | ZEND\_INIT\_DYNAMIC\_CALL                                                                                           | no               |
| 129    | ZEND\_DO\_ICALL                                                                                                     | no               |
| 130    | ZEND\_DO\_UCALL                                                                                                     | no               |
| 131    | ZEND\_DO\_FCALL\_BY\_NAME                                                                                           | no               |
| 132    | <a href="/internals2/opcodes/pre-inc-obj.html" class="xref">PRE_INC_OBJ</a>                                         | yes              |
| 133    | <a href="/internals2/opcodes/pre-dec-obj.html" class="xref">PRE_DEC_OBJ</a>                                         | yes              |
| 134    | <a href="/internals2/opcodes/post-inc-obj.html" class="xref">POST_INC_OBJ</a>                                       | yes              |
| 135    | <a href="/internals2/opcodes/post-dec-obj.html" class="xref">POST_DEC_OBJ</a>                                       | yes              |
| 136    | <a href="/internals2/opcodes/assign-obj.html" class="xref">ASSIGN_OBJ</a>                                           | yes              |
| 137    | ZEND\_OP\_DATA                                                                                                      | no               |
| 138    | <a href="/internals2/opcodes/instanceof.html" class="xref">INSTANCEOF</a>                                           | yes              |
| 139    | <a href="/internals2/opcodes/declare-class.html" class="xref">DECLARE_CLASS</a>                                     | yes              |
| 140    | <a href="/internals2/opcodes/declare-inherited-class.html" class="xref">DECLARE_INHERITED_CLASS</a>                 | yes              |
| 141    | <a href="/internals2/opcodes/declare-function.html" class="xref">DECLARE_FUNCTION</a>                               | yes              |
| 142    | <a href="/internals2/opcodes/raise-abstract-error.html" class="xref">RAISE_ABSTRACT_ERROR</a>                       | yes              |
| 143    | <a href="/internals2/opcodes/declare-const.html" class="xref">DECLARE_CONST</a>                                     | no               |
| 144    | <a href="/internals2/opcodes/add-interface.html" class="xref">ADD_INTERFACE</a>                                     | no               |
| 145    | <a href="/internals2/opcodes/declare-inherited-class-delayed.html" class="xref">DECLARE_INHERITED_CLASS_DELAYED</a> | no               |
| 146    | <a href="/internals2/opcodes/verify-abstract-class.html" class="xref">VERIFY_ABSTRACT_CLASS</a>                     | no               |
| 147    | <a href="/internals2/opcodes/assign-dim.html" class="xref">ASSIGN_DIM</a>                                           | yes              |
| 148    | <a href="/internals2/opcodes/isset-isempty-prop-obj.html" class="xref">ISSET_ISEMPTY_PROP_OBJ</a>                   | yes              |
| 149    | <a href="/internals2/opcodes/handle-exception.html" class="xref">HANDLE_EXCEPTION</a>                               | yes              |
| 150    | <a href="/internals2/opcodes/user-opcode.html" class="xref">USER_OPCODE</a>                                         | no               |
| 151    | ZEND\_ASSERT\_CHECK                                                                                                 | no               |
| 152    | <a href="/internals2/opcodes/zend-jmp-set.html" class="xref">ZEND_JMP_SET</a>                                       | no               |
| 153    | <a href="/internals2/opcodes/zend-declare-lambda-function.html" class="xref">ZEND_DECLARE_LAMBDA_FUNCTION</a>       | no               |
| 154    | ZEND\_ADD\_TRAIT                                                                                                    | no               |
| 155    | ZEND\_BIND\_TRAITS                                                                                                  | no               |
| 156    | ZEND\_SEPARATE                                                                                                      | no               |
| 157    | ZEND\_FETCH\_CLASS\_NAME                                                                                            | no               |
| 158    | ZEND\_CALL\_TRAMPOLINE                                                                                              | no               |
| 159    | ZEND\_DISCARD\_EXCEPTION                                                                                            | no               |
| 160    | ZEND\_YIELD                                                                                                         | no               |
| 161    | ZEND\_GENERATOR\_RETURN                                                                                             | no               |
| 162    | ZEND\_FAST\_CALL                                                                                                    | no               |
| 163    | ZEND\_FAST\_RET                                                                                                     | no               |
| 164    | ZEND\_RECV\_VARIADIC                                                                                                | no               |
| 165    | ZEND\_SEND\_UNPACK                                                                                                  | no               |
| 166    | ZEND\_POW                                                                                                           | no               |
| 167    | ZEND\_ASSIGN\_POW                                                                                                   | no               |
| 168    | ZEND\_BIND\_GLOBAL                                                                                                  | no               |
| 169    | ZEND\_COALESCE                                                                                                      | no               |
| 170    | ZEND\_SPACESHIP                                                                                                     | no               |
| 171    | ZEND\_DECLARE\_ANON\_CLASS                                                                                          | no               |
| 172    | ZEND\_DECLARE\_ANON\_INHERITED\_CLASS                                                                               | no               |
| 173    | ZEND\_FETCH\_STATIC\_PROP\_R                                                                                        | no               |
| 174    | ZEND\_FETCH\_STATIC\_PROP\_W                                                                                        | no               |
| 175    | ZEND\_FETCH\_STATIC\_PROP\_RW                                                                                       | no               |
| 176    | ZEND\_FETCH\_STATIC\_PROP\_IS                                                                                       | no               |
| 177    | ZEND\_FETCH\_STATIC\_PROP\_FUNC\_ARG                                                                                | no               |
| 178    | ZEND\_FETCH\_STATIC\_PROP\_UNSET                                                                                    | no               |
| 179    | ZEND\_UNSET\_STATIC\_PROP                                                                                           | no               |
| 180    | ZEND\_ISSET\_ISEMPTY\_STATIC\_PROP                                                                                  | no               |
| 181    | ZEND\_FETCH\_CLASS\_CONSTANT                                                                                        | no               |
| 182    | ZEND\_BIND\_LEXICAL                                                                                                 | no               |
| 183    | ZEND\_BIND\_STATIC                                                                                                  | no               |
| 184    | ZEND\_FETCH\_THIS                                                                                                   | no               |
| 185    | ZEND\_SEND\_FUNC\_ARG                                                                                               | no               |
| 186    | ZEND\_ISSET\_ISEMPTY\_THIS                                                                                          | no               |
| 187    | ZEND\_SWITCH\_LONG                                                                                                  | no               |
| 188    | ZEND\_SWITCH\_STRING                                                                                                | no               |
| 189    | ZEND\_IN\_ARRAY                                                                                                     | no               |
| 190    | ZEND\_COUNT                                                                                                         | no               |
| 191    | ZEND\_GET\_CLASS                                                                                                    | no               |
| 192    | ZEND\_GET\_CALLED\_CLASS                                                                                            | no               |
| 193    | ZEND\_GET\_TYPE                                                                                                     | no               |
| 194    | ZEND\_FUNC\_NUM\_ARGS                                                                                               | no               |
| 195    | ZEND\_FUNC\_GET\_ARGS                                                                                               | no               |
| 196    | ZEND\_UNSET\_CV                                                                                                     | no               |
| 197    | ZEND\_ISSET\_ISEMPTY\_CV                                                                                            | no               |

Pseudo-opcodes that are used only temporarily during compilation.

| Number | Name       | Has sample code? |
|--------|------------|------------------|
| 253    | ZEND\_GOTO | no               |
| 254    | ZEND\_BRK  | no               |
| 255    | ZEND\_CONT | no               |
