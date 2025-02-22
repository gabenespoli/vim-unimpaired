# gabenespoli/unimpaired.vim

This fork makes a few minor changes:

1. use `co` instead of `yo` for option mappings
2. remove experimental paste bindings, mostly so that I can bind `=` to
   something else without having it wait for a second character
3. remove the html string encoding; since I don't use this stuff, I don't need
   to load it and I would like to have `[y` and `]y` back

# unimpaired.vim

Much of unimpaired.vim was extracted from my vimrc when I noticed a
pattern: complementary pairs of mappings.  They mostly fall into four
categories.

There are mappings which are simply short normal mode aliases for
commonly used ex commands. `]q` is :cnext. `[q` is :cprevious. `]a` is
:next.  `[b` is :bprevious.  See the documentation for the full set of
20 mappings and mnemonics.  All of them take a count.

There are linewise mappings. `[<Space>` and `]<Space>` add newlines
before and after the cursor line. `[e` and `]e` exchange the current
line with the one above or below it.

There are mappings for toggling options. `[os`, `]os`, and `yos` perform
`:set spell`, `:set nospell`, and `:set invspell`, respectively.  There's also
`l` (`list`), `n` (`number`), `w` (`wrap`), `x` (`cursorline cursorcolumn`),
and several others, plus mappings to help alleviate the `set paste` dance.
Consult the documentation.

There are mappings for encoding and decoding. `[x` and `]x` encode and
decode XML (and HTML). `[u` and `]u` encode and decode URLs. `[y` and
`]y` do C String style escaping.

And in the miscellaneous category, there's `[f` and `]f` to go to the
next/previous file in the directory, and `[n` and `]n` to jump between
SCM conflict markers.

The `.` command works with all operator mappings, and will work with the
linewise mappings as well if you install
[repeat.vim](https://github.com/tpope/vim-repeat).

## Installation

Install using your favorite package manager, or use Vim's built-in package
support:

    mkdir -p ~/.vim/pack/tpope/start
    cd ~/.vim/pack/tpope/start
    git clone https://tpope.io/vim/unimpaired.git
    vim -u NONE -c "helptags unimpaired/doc" -c q

## FAQ

> My non-US keyboard makes it hard to type `[` and `]`.  Can I configure
> different prefix characters?

The easiest solution is to map to `[` and `]` directly:

    nmap < [
    nmap > ]
    omap < [
    omap > ]
    xmap < [
    xmap > ]

Note we're not using the `noremap` family because we *do* want to recursively
invoke unimpaired.vim's maps.

## Contributing

See the contribution guidelines for
[pathogen.vim](https://github.com/tpope/vim-pathogen#readme).

## Self-Promotion

Like unimpaired.vim? Follow the repository on
[GitHub](https://github.com/tpope/vim-unimpaired) and vote for it on
[vim.org](http://www.vim.org/scripts/script.php?script_id=1590).  And if
you're feeling especially charitable, follow [tpope](http://tpo.pe/) on
[Twitter](http://twitter.com/tpope) and
[GitHub](https://github.com/tpope).

## License

Copyright (c) Tim Pope.  Distributed under the same terms as Vim itself.
See `:help license`.
