# Binary-Coded Decimal (BCD)

Binary-coded decimal, or BCD, is a way to store numbers in memory. A single digit in a BCD number is stored in its base-10 form in one nibble of a byte. 

## When to use BCD encoding
- For numbers that will be displayed in base 10 (like a score)
- For numbers that scale by factors of 10
- For decimal arithmetic (probably less relevant, unless you're writing financial software for the Game Boy) 

## References
- z80 and 8080 assembly language programming
- https://en.wikibooks.org/wiki/Practical_Electronics/Binary-coded_Decimal
- http://www.idc-online.com/technical_references/pdfs/electronic_engineering/Binary_Coded_Decimal.pdf

## TODO
- Little- vs. big-endian in memory
- Is BCD better for large numbers? (i.e., bigger than $FFFF) Or is it the same amount of bad since BCD numbers are worked from memory?
- Packed vs. unpacked 
- Example: game scores
