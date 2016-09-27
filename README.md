Homoglyph Finder
================

This is actually just a copy of [homoglyph-search](https://github.com/codebox/homoglyph) JS module with a few changes:
1. ES6 `for-of` loop has been removed for a better browser support;
2. there is a new `isMatches` function (see its usage below).

## Description

This module provides a homoglyph-aware search function that allows you to find target words within a piece of text, even if the words have been disguised using homoglyph characters.

Homoglyphs are characters with different meanings, that look similar/identical to each other - like the digit '0' and the capital letter 'O' for example.

Homoglyphs within a single alphabet tend to be rare for obvious reasons. These days, however, the internet runs on Unicode which means that it is possible to mix the letters from many [different languages](http://www.unicode.org/cldr/charts/latest/supplemental/languages_and_scripts.html) together in one place, massively increasing the number of homoglyphs.

For example, each of the characters shown below are different, with their own unique Unicode codepoint values, but they all look more-or-less like the capital letter 'A':

A Α А Ꭺ ᗅ ᴀ ꓮ Ａ 𐊠 𝐀 𝐴 𝑨 𝒜 𝓐 𝔄 𝔸 𝕬 𝖠 𝗔 𝘈 𝘼 𝙰 𝚨 𝛢 𝜜 𝝖 𝞐

As well as creating general confusion, homoglyphs can cause particular problems for software developers. For example, if a social media website wants to protect its users from offensive language it may create a 'black-list' of forbidden words, and block any content that contains them. However, someone wishing to use one of the black-listed words could replace one of its letters with a homoglyph - the word would no longer match the one on the black-list, but its meaning would still be apparent to anyone who saw it.

## Installation

    npm install homoglyph-finder

## Usage

    var finder = require('homoglyph-finder');

    finder.search('Get free ϲrEd1ᴛ', ['credit']);

    finder.isMatches('ϲrEd1ᴛ', 'credit'); // returns true
    finder.isMatches('Get free ϲrEd1ᴛ', 'credit'); // returns false

## Tests

    npm test

## Links
* [Original project](http://codebox.org.uk/pages/homoglyph-detection)
* [GitHub](https://github.com/codebox/homoglyph)
