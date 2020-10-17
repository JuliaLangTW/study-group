
class: center, middle






# Integer and Floating points






### Julia Study Group






#### Yueh-Hua Tu






#### 2020.10.17


---






# Outline


  * Integer
  * Floating points


---






# Integer


  * `Int8`
  * `Int16`
  * `Int32`
  * `Int64`


--






### Default integer


  * `Int`
  * `Sys.WORD_SIZE`


---






# Binary representation of integer


  * `7` => `0000 0111`
  * range: $-2^7 \sim 2^7 - 1$ for 8-bit


--






### Binary representation in Julia


  * `bitstring`


--






### Try (in 8-bit)


  * -1
  * 127
  * 128
  * -127
  * -128


---






# Complements (補數)


Complement system is a representation for signed integer. There are two ways:


--






### Two's complement (8 bits)


  * `1`: `0000 0001`
  * `0`: `0000 0000`
  * `-1`: `1111 1111`


--






### One's complement (8 bits)


  * `1`: `0000 0001`
  * `0`: `0000 0000`
  * `-1`: `1111 1110`


---






# Unsigned integer


  * `UInt8`
  * `UInt16`
  * `UInt32`
  * `UInt64`


--






### Binary representation


--






### Try


  * `0x123`


---






# Overflow


  * `Int8(127) + Int8(1)`


```
julia> bitstring(Int8(127))
"01111111"

julia> bitstring(Int8(1))
"00000001"
```


--


```
julia> bitstring(Int8(-128))
"10000000"
```


--






### Another example


  * `Int(-128) - Int(1)`


```
julia> bitstring(Int8(-128))
"10000000"

julia> bitstring(Int8(1))
"00000001"
```


---






# Floating point


  * `Float16`
  * `Float32`
  * `Float64`


--






### Size of value in memory


  * `sizeof`


--




### Try


  * `1.`
  * `.1`
  * `1e5`
  * `1e-5`
  * `2.5f0`
  * `typeof(2.5f0)`
  * `2.5f-4`
  * `sizeof(2.5f-4)`


---






# Binary representation of floating point


  * `bitstring(1.0)`
  * `bitstring(-1.0)`
  * `bitstring(Float16(2.0))`
  * `bitstring(Float16(1024.))`
  * `bitstring(Float16(2048.))`
  * `bitstring(Float16(4096.))`


---






# Machine epsilon


The relative error due to rounding in floating point arithmetic.


  * `eps`


--




### Try


  * `eps(Float64)`
  * `eps(Float32)`
  * `eps()`
  * `eps(1.0)`


---






# Extreme value for types


  * `typemax`
  * `typemin`


--




### Try


  * `typemax(Int64)`
  * `typemax(Int32)`
  * `typemax(Int16)`


---






# Arithmatic operations


  * `+`
  * `-`
  * `*`
  * `/`
  * `%` or `rem`
  * `div`
  * `^`
  * `sqrt`
  * `abs2`
  * `abs`


---






# Comparison operations


  * `>`
  * `=`
  * `<`
  * `≤` or `<=`
  * `≥` or `>=`
  * `≠` or `!=`


---






# Conversion between integer and floating point


  * `Integer(1.0)`
  * `Int(1.0)`
  * `Int(1.1)`
  * `Float64(1)`


---






# Transcendental function (超越函數)


  * `sin`
  * `cos`
  * `tan`
  * `exp`
  * `log`
  * `log2`
  * `log10`
  * `log1p`


---






# Round, ceiling and floor


  * `round`
  * `ceil`
  * `floor`


--




### Try


  * `round(7.321, digits=2)`
  * `ceil(7.321, digits=1)`
  * `floor(7.321, digits=2)`
  * `ceil(7, base=8)`


---






# Infinity and not a number


  * `Inf`, `Inf32`, `Inf16`
  * `NaN`, `NaN32`, `NaN16`


--






### Arithmetic operations


  * `Inf + 1`
  * `Inf - Inf`
  * `1/Inf`
  * `1/0`
  * `Inf == Inf`
  * `0/0`
  * `NaN + 1`
  * `0*Inf`
  * `Inf/Inf`


---






# Standard input and parsing


  * `readline()`
  * `parse`


--






### Practice: BMI calculator


$$ bmi = \frac{weight (kg)}{height^2 (m)} $$


--






### Practice: Compound interest


$$ interest = base(1 + \frac{r}{n})^{nt} $$


---






# If-else


```
if <condition>
    <do something>
elseif <condition>
    <do another thing>
else
    <do other thing>
end
```


---






# Random numbers


  * `rand()`
  * `rand(10)`
  * `rand(3, 4)`
  * `rand([0, 1])`


--




### Try


  * generate a uniform-distributed random number from 1.23 ~ 5.67


---


class: middle






# Thank you for attention

