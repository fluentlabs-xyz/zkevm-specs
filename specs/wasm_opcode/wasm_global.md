# GLOBAL (GET/SET) opcode

- GetGlobal = OpcodeId(**0x23**)
- SetGlobal = OpcodeId(**0x24**)

## Procedure

One of the following procedure is done:
 - Gets the value of a global variable at a specified index
 - Sets the value of a global variable at a specified index


## Constraints

1. state transition:
   - rw_counter + 2
   - stack_pointer + sp 
     - sp is +1 for SetGlobal
     - sp is -1 for GetGlobal
   - pc + 1
   - gas + 120
2. Lookups: one of following busmapping lookup
   - `value` is at the given index on the stack (read operation)
   - `value` is written to at the given index of the stack (write operation)

## Exceptions

1. not found index value: when the given value and index are not found (**NTY**)
2. gas out: remaining gas is not enough (**NTY**)

## Code

See `src/zkevm_specs/wasm/execution/global.py` (**NIY**))
