## Data types

`char`  8 bits = 1 byte
    
    - unsigned char: 0 - 255
    - [signed] char: -128 - 127

`short` 16 bits = 2 bytes

    - unsigned short: 0 - 65,535
    - short: -32,768 - 32,767

`int` 32 bits = 4 bytes

    - unsigned: 0 - 4,294,967,295
    - int: -2,147,483,648 - 2,147,483,647

`long` 64 bits = 8 bytes

    - unsigned long: 0 - 18,446,744,073,709,551,615
    - long: -9,223,372,036,854,775,808 - 9,223,372,036,854,775,807

## Encodings

- Define function Binary to Unsigned $$B2U_w(\vec{x}) = \sum_{i=0}^{w-1}x_i2^i$$ for $\vec{x}=[x_{w-1}, x_{w-2}, \dots, x_0]$
    - Min value = 0
    - Max value = $2^w-1$

- Define function Binary to Two's Complement $$B2T_w(\vec{x}) = -x_{w-1}\cdot2^{w-1}+\sum_{i=0}^{w-2}x_i2^i$$ for $\vec{x}=[x_{w-1}, x_{w-2}, \dots, x_0]$
    - Min value = $-2^w-1$
    - Max value = $2^{w-1}-1$

## Conversion between Signed and Unsigned

- Principle: Bit representation does not change

- Signed to unsigned conversion: $$T2U_w(x) = \begin{cases} 
x+2^w & x < 0 \\
x & x \geq 0
\end{cases}$$
for $-2^w-1 \leq x \leq 2^{w-1}-1$.

- Unsigned to signed conversion:
<img src="https://latex.codecogs.com/png.image?\dpi{110}\bg{black}\begin{cases}u&u\leq&space;2^{w-1}-1\\u-2^w&u>2^{w-1}-1\end{cases}" title="\begin{cases}u&u\leq 2^{w-1}-1\\u-2^w&u>2^{w-1}-1\end{cases}" />

## MERMAID
[![](https://mermaid.ink/img/pako:eNq9VdFu2jAU_RXrPtGNICAkJVbFw1Z1m7RK08bT5BcruUkjiI2MM5UhvmifsLd-2WxnoUkJ0HbSnmLfe865PtdX8RZimSBQ8DyPiViKNM8oE4QspVxQIlDajb7DAikpYpfhG1lqSnC5YKKiLfl6fZ3zTPGCiSRXGOtcCjJ_Z_GEuDy5lnFZoNA3PNZSbciWCaZt-i2JFXKNX1EkqFD1Lki9fAq5kUKbtP1U0juD6KjxAQUqbso0q2RVEHvftMpFdkF-yDzplLH6TSZfrZab3gnCx_nt57P-Wod_hvUjdV51uFq1SVQuNsd7fb4jX5L0f9yfKfNie4bzr-5ex2f66uqT0KhSHuNs9nTADwH1zbejjV457cMZZjBiQN543swsU9sfu39s4hmGqt3ZWHu8uuZ2MOiwcgq8H0pKHn5V9_zw-zxl3_RumlO02EefLZZNtc10zOhRL0ew9fwdHuk44YSPWq5to8lpuoA-ZCpPgKZ8ucY-FKgKbvewtUQG7jfMgJplwtWCARM7Q1px8V3KAqhWpaEpWWZ3e5FylZgD_f057yGu4ntZCg10FDgJoFu4Nzs_HFxG08nIH4fBOJqEfdgADaPBOIrCcTAaTsNgOJzu-vDT1RwOonE4nUS-QfsT_zIY9QGT3DTotnpY3Puy-wPbMBqe?type=png)](https://mermaid.live/edit#pako:eNq9VdFu2jAU_RXrPtGNICAkJVbFw1Z1m7RK08bT5BcruUkjiI2MM5UhvmifsLd-2WxnoUkJ0HbSnmLfe865PtdX8RZimSBQ8DyPiViKNM8oE4QspVxQIlDajb7DAikpYpfhG1lqSnC5YKKiLfl6fZ3zTPGCiSRXGOtcCjJ_Z_GEuDy5lnFZoNA3PNZSbciWCaZt-i2JFXKNX1EkqFD1Lki9fAq5kUKbtP1U0juD6KjxAQUqbso0q2RVEHvftMpFdkF-yDzplLH6TSZfrZab3gnCx_nt57P-Wod_hvUjdV51uFq1SVQuNsd7fb4jX5L0f9yfKfNie4bzr-5ex2f66uqT0KhSHuNs9nTADwH1zbejjV457cMZZjBiQN543swsU9sfu39s4hmGqt3ZWHu8uuZ2MOiwcgq8H0pKHn5V9_zw-zxl3_RumlO02EefLZZNtc10zOhRL0ew9fwdHuk44YSPWq5to8lpuoA-ZCpPgKZ8ucY-FKgKbvewtUQG7jfMgJplwtWCARM7Q1px8V3KAqhWpaEpWWZ3e5FylZgD_f057yGu4ntZCg10FDgJoFu4Nzs_HFxG08nIH4fBOJqEfdgADaPBOIrCcTAaTsNgOJzu-vDT1RwOonE4nUS-QfsT_zIY9QGT3DTotnpY3Puy-wPbMBqe)
