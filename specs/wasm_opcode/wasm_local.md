# Local (GET/SET) opcode

- GetLocal = OpcodeId(**0x20**)
- SetLocal = OpcodeId(**0x21**)
- TeeLocal = OpcodeId(**0x22**)

## Procedure

One of the following procedure is done:
 - Gets the value of a local variable at a specified index
 - Sets the value of a local variable at a specified index
 - Sets the value of a local variable at a specified index and also pushes the value onto the stack

## Constraints

1. state transition:
   - rw_counter + 2
   - pc + 1
   - stack_pointer + sp
      - sp is +1 for SetLocal
      - sp is -1 for GetLocal
      - sp is 0 for TeeLocal
   - gas + 120
2. Lookups: one of following busmapping lookup
   - `value` is at the given index on the stack (read operation)
   - `value` is written to at the given index of the stack (write operation)

## Exceptions

1. not found index value: when the given value and index are not found (**NTY**)
2. gas out: remaining gas is not enough (**NTY**)

## Code

See `src/zkevm_specs/wasm/execution/local.py` (**NIY**))
