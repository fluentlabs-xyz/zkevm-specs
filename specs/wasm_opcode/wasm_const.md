# CONST opcode

- I32Const opId = OpcodeId(**0x41**)
- I64Const opId = OpcodeId(**0x42**)

## Procedure

Pushes a 32/64-bit integer constant onto the stack.

## Constraints

1. state transition:
   - rw_counter + 1
   - stack_pointer - 1
   - pc + 1
   - gas + 1
2. Lookups: 1 busmapping lookup
   - `value` is written to at the top of the stack (write operation)

## Exceptions

1. stack overflow: when stack is full (**NTY**)
2. gas out: remaining gas is not enough (**NTY**)

## Code

See `src/zkevm_specs/wasm/execution/const.py` (**NIY**))
