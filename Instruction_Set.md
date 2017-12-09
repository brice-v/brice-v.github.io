__Instruction Set__ 
===
>_Accumulator based 8-bit Processor_
_By Brice Vadnais and Aristotle Nafpliotis
---

#### Inherent Instructions
___```nop``` - No Operation___
  * Format: ```nop``` - Stalls the Processor for one clock cycle

___```add_acc``` - Add Accumulator A & B together and store result in Accumulator C___
  * Format: ```add```

___```sub_acc``` - Subtract Accumulator A from B and store result in Accumulator C___
  * Format: ```sub```

___```hlt``` - Halt operation of the processor___
  * Format: ```hlt``` 

___```inc_a``` - Increment Accumulator A___
  * Format: ```inca``` - Increases Accumulator A by 1

___```inc_b``` - Increment Accumulator B___
  * Format: ```incb``` - Increases Accumulator B by 1

___```dec_a``` - Decrement Accumulator A___
  * Format: ```deca``` - Decreases Accumulator A by 1

___```dec_b``` - Decrement Accumulator B___
  * Format: ```decb``` - Decreases Accumulator B by 1

___```mul_acc``` - Multiply Accumulators A & B___
  * Format: ```mul``` - Stores value in Accumulator C

___```div_acc``` - Floor Division of Accumulator A into B___
  * Format: ```div``` - Stores value in Accumulator C

___```cmp_acc``` - Compare Accumulators___
  * Format: ```cmp``` - Sets Zero, Negative, and Carry flags according to accumulators

___```jmp_neq``` - Jump when Zero Flag is low (Implying Accumulators are equal)___
  * Format: ```jne [REF]``` or ```jne 0xXX``` or ```jne [0xXX]```  

---

#### Immediate Instructions
___```lda_imm``` - Load Accumulator A with immediate 8-bit value___
  * Format: ```lda 0xXX``` - Loads A with 8 bit hex value 0xXX

___```ldb_imm``` - Load Accumulator B with immediate 8-bit value___
  * Format: ```ldb 0xXX``` - Loads B with 8-bit hex value 0xXX

___```adda_imm``` - Add Accumulator A with immediate 8-bit value___
  * Format: ```adda 0xXX``` - Adds the 8-bit hex value 0xXX to Accumulator A 

___```addb_imm``` - Add Accumulator B with immediate 8-bit value___
  * Format: ```addb 0xXX``` - Adds the 8-bit hex value 0xXX to Accumulator B

___```suba_imm``` - Subtract an 8-bit value from Accumulator A___
  * Format: ```suba 0xXX``` - Subtracts the 8-bit hex value, 0xXX, from Accumulator A

___```subb_imm``` - Subtract an 8-bit value from Accumulator B___
  * Format: ```subb 0xXX``` - Subtracts the 8-bit hex value, 0xXX, from Acuumulator B 

___```ldx_imm``` - Load Accumlator X with immediate 8-bit value___
  * Format: ```ldx 0xXX``` - Loads index accumulator with 8-bit hex value 0xXX

___```lds_imm``` - Load Accumulator S with immediate 8-bit value___
  * Fornat: ```lds 0xXX``` - Lods stack pointer accumulator with 8-bit hex value

___```jmp_imm``` - Jump to Immediate 8-bit value___
  * Format: ```jmp 0xXX``` - Jumps to the 8-bit hex value 0xXX

---

#### Direct/Extended (Memory) Instructions 
___```lda_dir``` - Load Accumulator A with memory value___
  * Format: ```lda [0xXX]``` or ```lda [REF]``` - Loads the A Accumulator with the 8-bit hex value located at [0xXX] or [REF]

___```ldb_dir``` - Load Accumulator B with memory value___
  * Format: ```ldb [0xXX]``` or ```ldb [REF]``` - Loads the B Accumulator with the 8-bit hex value located at [0xXX] or [REF]

___```adda_dir``` - Add value from memory to Accumulator A___
  * Format: ```adda [0xXX]``` or ```adda [REF]``` - Adds to Accumulator A the 8-bit hex value located at memory location [0xXX] or [REF]

___```addb_dir``` - Add value from memory to Accumulator B___
  * Format: ```addb [0xXX]``` or ```addb [REF]``` - Adds to Accumulator B the 8-bit hex value located at memory location [0xXX] or [REF]

___```suba_dir``` - Subtract value in memory from Accumulator A___
  * Format: ```suba [0xXX]``` or ```suba [REF]``` - Subtracts the 8-bit hex value, located at [0xXX] or [REF], in memory from Accumulator A

___```subb_dir``` - Subtract value in memory from Accumulator B___
  * Format: ```subb [0xXX]``` or ```subb [REF]``` - Subtracts the 8-bit hex value, located at [0xXX] or [REF], in memory from Accumulator B

___```sta_ref``` - Store Accumulator A value in memory___
  * Format: ```sta [0xXX]``` or ```sta [REF]``` - The 8-bit hex value in Accumulator A is stored in memory location [0xXX] or [REF] 

___```stb_ref``` - Store Accumulator B value in memory___
  * Format: ```stb [0xXX]``` or ```stb [REF]``` - The 8-bit hex value in Accumulator B is stored in memory location [0xXX] or [REF]

___```ldx_dir``` - Load Accumulator X with value in memory___
  * Format: ```ldx [0xXX]``` or ```ldx [REF]``` - Loads Index Accumulator with 8-bit hex value from memory location [0xXX] or [REF]

___```lds_dir``` - Load Accumulator S with value in memory___
  * Format: ```lds [0xXX]``` or ```lds [REF]``` - Loads Stack Pointer with 8-bit hex value from memory location [0xXX] or [REF]

___```dec_dir``` - Decrement the value at location in memory___
  * Format: ```dec [0xXX]``` or ```dec [REF]``` - Decreases value at memory location [0xXX] or [REF] by 1

___```inc_dir``` - Increment the value at location in memory___
  * Format: ```inc [0xXX]``` or ```inc [REF]``` - Increases value at memory location [0xXX] or [REF] by 1

___```jmp_dir``` - Jump to point in memory___
  * Format: ```jmp [0xXX]``` or ```jmp [REF]``` - Jumps to location at memory location 0xXX or REF

---

#### Stack Instructions
___```push_a``` - Push Accumulator A into Stack___
  * Format: ```psha``` -  Load Accumulator A 8-bit hex value into stack
  * Pre decrement - Stack Pointer is decreased by 1 before operation

___```pop_a``` - Pop Value from Stack into Accumulator A___
  * Format: ```popa``` - Load Accumulator A with value at Stack Pointer
  * Post increment - Stack Pointer is increased by 1 after operation

___```push_b``` - Push Accumulator B into Stack___
  * Format: ```pshb``` - Load Accumulator B 8-bit hex value into stack
  * Pre decrement - Stack Pointer is decreased by 1 before operation

___```pop_b``` - Pop Value from Stack into Accumulator B___
  * Format: ```popb``` - Load Accumulator B with value at Stack Pointer
  * Post increment - Stack Pointer is increased by 1 after operation

___```push_imm``` - Push immediate value into Stack___
  * Format: ```psh 0xXX``` - Push immediate 8-bit hex value 0xXX into stack
  * Pre decrement - Stack Pointer is decreased by 1 before operation

___```push_dir``` - Push value in memory to Stack___
  * Format: ```psh [0xXX]``` or ```psh [REF]``` - Push value at memory location [0xXX] or [REF] to the Stack
  * Pre decrement - Stack Pointer is decreased by 1 before operation

___```push_indx``` - Push the Indexed value in memory to Stack___
  * Format: ```psh [y + X]``` - Push value at y plus value of indexed Accumulator X onto stack
  * Pre decrement - Stack Pointer is decreased by 1 before operation 

---

#### Indexed Instructions
___```lda_indx``` - Load Accumulator A with Indexed value in memory___
  * Format: ```lda [y + X]``` - Load the value located at y plus the value of indexed accumulator X into Accumulator A

___```ldb_indx``` - Load Accumulator B with Indexed value in memory___
  * Format: ```ldb [y + X]``` - Load the value located at y plus the value of indexed accumulator X into Accumulator B

___```sta_indx``` - Store Accumulator A to Indexed value in memory___
  * Format: ```sta [y + X]``` - Store Accumulator A into memory at location y plus the value of indexed Accumulator X  

___```stb_indx``` -  Store Accumulator B to Indexed value in memory___
  * Format: ```stb [y + X]``` - Store Accumulator B into memory at location y plus the value of indexed Accumulator X

___```inc_indx``` - Increment Value at Indexed value in memory___
  * Format: ```inc [y + X]``` - Increment value at y plus the value of indexed Accumulator X

___```dec_indx``` - Decrement Value at Indexed value in memory___
  * Format: ```dec [y + X]``` - Decrement value at y plus the value of indexed Accumulator X

___```jmp_indx``` - Jump to value at Indexed value in memory___
  * Format: ```jmp [y + X]``` - Jump to value at y plus the value of indexed Accumulator X
