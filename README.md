# Semantic Line Breaks

## Summary

When writing text using a compatible markup language,
add single line breaks after substantial units of thought.

## Introduction

_Semantic Line Breaks_ describes a set of conventions by which
writers insert single line breaks at semantic boundaries
without affecting the final rendered output.

Many of the most popular lightweight markup language renderers,
including
[CommonMark][commonmark]
[reStructuredText][restructuredtext], and
[AsciiDoc][asciidoc],
join consecutive lines in a paragraph with a space,
allowing semantic line breaks to be used.
In addition, semantic line breaks can be used in certain contexts
of HTML, XML, and other structured markup language documents.

To better understand the benefit of semantic line breaks,
consider the following paragraph from the
[_Universal Declaration of Human Rights_][udhr]:

> All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

Without any semantic line breaks,
this paragraph appears as a long, continuous line of text
(which may be automatically wrapped at a fixed column length,
depending on your editor settings):

<pre>
All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.
</pre>

Adding a semantic line break after each sentence
makes it easier to understand the shape and structure of the source text:

<pre>
All human beings are born free and equal in dignity and rights.
They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.
</pre>

We can further clarify the source text by adding a line break after
the clause "with reason and conscience".
This helps to distinguish between the "and" used as a
coordinating conjunctions between "reason and conscience"
and the "and" used as a subordinating conjunction with the clause
"and should act towards one another in a spirit of brotherhood":

<pre>
All human beings are born free and equal in dignity and rights.
They are endowed with reason and conscience
and should act towards one another in a spirit of brotherhood.
</pre>

Despite these changes made to the source,
the final rendered output remains the same:

> All human beings are born free and equal in dignity and rights.
> They are endowed with reason and conscience
> and should act towards one another in a spirit of brotherhood.

By inserting line breaks at semantic boundaries,
writers, editors, and other collaborators
can make source text easier to work with,
without affecting how it's seen by readers.

## Semantic Line Breaks Specification (SemBr)

The key words "MUST", "MUST NOT", "REQUIRED",
"SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
"RECOMMENDED", "MAY", and "OPTIONAL"
in this document are to be interpreted as described in
[RFC 2119][rfc2119].

1. Text written as plain text or a compatible markup language
   MAY use semantic line breaks.
2. A semantic line break
   MUST NOT alter the final rendered output of the document.
3. A semantic line break
   SHOULD NOT alter the intended meaning of the text.
4. A semantic line break
   MUST occur after a sentence,
   as punctuated by a period (.),
   exclamation mark (!), or
   question mark (?).
5. A semantic line break
   SHOULD occur after an independent clause
   as punctuated by a comma (,),
   semicolon (;),
   colon (:),
   or em dash (—).
6. A semantic line break
   MAY occur after a dependent clause
   in order to clarify grammatical structure or satisfy line length constraints.
7. A semantic line break
   is RECOMMENDED before an enumerated or itemized list.
8. A semantic line break
   MAY be used after one or more items in a list
   in order to logically group related items or satisfy line length constraints.
9. A semantic line break
   MUST NOT occur within a hyphenated word.
10. A semantic line break
    MAY occur before and after a hyperlink.
11. A semantic line break
    MAY occur before inline markup.
12. A maximum line length of 80 characters is RECOMMENDED.
13. A line MAY exceed the maximum line length if necessary,
    such as to accommodate hyperlinks, code elements, or other markup.

## Why Use Semantic Line Breaks?

For a **writer**,
semantic line breaks allow the physical structure of text
to reflect the logical structure of the thoughts that produce them.

For an **editor**,
semantic line breaks make it easier to identify grammatical mistakes,
and find opportunities to simplify and clarify without altering original intent.

For a **reader**,
semantic line breaks are entirely invisible —
no changes to the source text appear in the final rendered output.

## FAQ

<dl>

<dt>Which light markup languages support semantic line breaks?</dt>
<dd>

The following light markup languages
are verified to support semantic line breaks:

- [AsciiDoc][asciidoc]
- [CommonMark][commonmark]
- [Haddock Markup][haddock-markdown]
- [Markdown][markdown]
- [MediaWiki][mediawiki]
- [MultiMarkdown][multimarkdown]
- [OrgMode][orgmode]
- [reStructuredText][restructuredtext]

<dt>How do I know when to add semantic line breaks?</dt>
<dd>

Try reading the text out loud,
as if you were speaking to an audience.
Anywhere that you pause for emphasis
or to take a breath
is a usually a good candidate for a semantic line break.

</dd>

<dt>How do I migrate existing prose to use semantic line breaks?</dt>
<dd>

There is no need to rewrite or reformat an entire document all at once.
The recommended migration path for an existing document
is to use semantic line breaks for any new or revised text.
This is often a great opportunity to make an editorial pass over content,
since the distinctive appearance of text with semantic line breaks
allows you to quickly identify content that has not been updated.

</dd>

<dt>How do I use semantic line breaks with Git?</dt>
<dd>

The default Git diff options emphasize line changes
in a way that may obscure certain revisions to text with semantic line breaks.
You can pass the `--word-diff` option to the `git diff` command
for better results:
`$ git diff --word-diff`

</dd>

<dt>How do I force a line break?</dt>
<dd>

The easiest way to force a line break is to insert a `<br/>` element.
Although some lightweight markup languages insert a line break
after lines with two trailing spaces,
this may be inadvertently broken
by editors that automatically strip trailing whitespace.

</dd>

</dl>

## About

This specification is an attempt to encapsulate best practices
that I've encountered while working on technical writing teams
at several different companies.
It follows the general structure of the
[Semantic Versioning specification][semver] by Tom Preston-Werner.

In the process of developing this document,
I came across
[this excellent blog post][one-sentence-per-line] by Brandon Rhodes
that includes extensive research about the origin of this technique.

If you’d like to leave feedback, please
[open an issue on GitHub][github-issues].

## License

[Creative Commons Attribution 4.0 International (CC BY 4.0)][cc-by-4.0]

[udhr]: http://www.un.org/en/universal-declaration-human-rights/
[rfc2119]: https://www.ietf.org/rfc/rfc2119
[asciidoc]: http://asciidoc.org
[commonmark]: http://commonmark.org
[haddock-marku]: https://www.haskell.org/haddock/doc/html/
[markdown]: https://daringfireball.net/projects/markdown/
[mediawiki]: https://www.mediawiki.org/wiki/Help:Formatting
[multimarkdown]: http://fletcherpenney.net/multimarkdown/
[orgmode]: http://orgmode.org
[restructuredtext]: http://docutils.sourceforge.net/rst.html
[semver]: http://semver.org
[one-sentence-per-line]: http://rhodesmill.org/brandon/2012/one-sentence-per-line/
[github-issues]: https://github.com/sembr/specification/issues
[cc-by-4.0]: https://creativecommons.org/licenses/by/4.0/