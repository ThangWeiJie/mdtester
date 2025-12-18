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
```mermaid
classDiagram
direction BT
class DocumentFactory {
<<Interface>>
  + createRenderer() Renderer
  + createFont() Font
}
class DocumentGenerator {
  + generate(String) void
}
class Font {
<<Interface>>
  + apply() void
}
class HTMLDocumentFactory {
  + createFont() Font
  + createRenderer() Renderer
}
class HTMLFont {
  + apply() void
}
class HTMLRenderer {
  + renderText(String) void
}
class PdfDocumentFactory {
  + createRenderer() Renderer
  + createFont() Font
}
class PdfFont {
  + apply() void
}
class PdfRenderer {
  + renderText(String) void
}
class Renderer {
<<Interface>>
  + renderText(String) void
}

DocumentGenerator "1" *--> "font 1" Font 
DocumentGenerator "1" *--> "renderer 1" Renderer 
HTMLDocumentFactory  ..>  DocumentFactory 
HTMLDocumentFactory  ..>  HTMLFont : «create»
HTMLDocumentFactory  ..>  HTMLRenderer : «create»
HTMLFont  ..>  Font 
HTMLRenderer  ..>  Renderer 
PdfDocumentFactory  ..>  DocumentFactory 
PdfDocumentFactory  ..>  PdfFont : «create»
PdfDocumentFactory  ..>  PdfRenderer : «create»
PdfFont  ..>  Font 
PdfRenderer  ..>  Renderer 

```
