# Data Encoding - TryHackMe

## 1. ASCII

**ASCII** stands for American Standard Code for Information Interchange, and it is an early character encoding from 1963 that uses numbers 0-127 to represent English letters, digits, punctuation, and some control characters.

**ASCII** provided a way to encode the English alphabet; however, we need an encoding to support other European languages\

The **ISO/IEC 8859 Series** (International Standards) created several standards; each standard covered a set of languages:

- ISO-8859-1 (Latin-1): Covered Western European languages.
- ISO-8859-2 (Latin-2): Supported Central/Eastern European languages.

## 2. Unicode

Unicode is a universal character encoding standard. It assigns unique code points to characters from all modern and historical writing systems worldwide. Unicode supports the interchange, processing, and display of text in diverse languages.
Unicode is a character set standard that assigns a unique number to every character across all languages.

### UTF-8, UTF-16, and UTF-32

- UTF-8 is very common on the modern web. It encodes Unicode points into 1 to 4 bytes dynamically.
- UTF-16 it uses either 2 or 4 bytes per character.
- UTF-32 is the simplest but also the most wasteful; every Unicode code point uses exactly 4 bytes.