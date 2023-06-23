# DROP opcode

- Drop opId = OpcodeId(**0x1a**)

## Procedure

A stack initalize empty with stack pointer to 1024. This opcode drops the top value from the stack. A stack drop operation can only happen when stack is not empty, and it will increase by 1 of stack pointer.


## Constraints

1. state transition:
   - rw_counter + 1
   - stack_pointer + 1
   - pc + 1
   - gas + 2
2. Lookups: 1 busmapping lookup
   - `value` is at the top of the stack

## Exceptions

1. stack underflow: when stack is empty (**NTY**)
2. gas out: remaining gas is not enough (**NTY**)

## Code

See `src/zkevm_specs/wasm/execution/drop.py` (**NIY**))
