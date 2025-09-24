README (as requested, outside the ZIP)
What you’re getting

A folder for each chapter: Chapter_01, Chapter_02, … up to Chapter_15.

Inside each chapter, files are named using either the original path I detected in the text (e.g., lib/core/core.ml) or a fallback like snippet_001.ml when a filename wasn’t specified.

Non-OCaml support files (e.g., dune, .opam entries, CI YAML, command snippets) are included when they appeared as code blocks.

How I detected code

I parsed the DOCX and captured code blocks using a mix of signals: OCaml keywords (let, module, type, open, match, Cmdliner, Eio, Alcotest), Dune/OPAM stanzas, and shell commands shown as install/build steps.

When the book listed a filepath (e.g., apps/cli/main.ml), I used that exact path as the saved filename.

When no filename was present, I saved the block as snippet_###.ml in that chapter.

Quick counts

Total files extracted: 399

Per chapter:

Chapter_00: 5 files

Chapter_01: 51 files

Chapter_02: 57 files

Chapter_03: 28 files

Chapter_04: 38 files

Chapter_05: 37 files

Chapter_06: 36 files

Chapter_07: 31 files

Chapter_08: 15 files

Chapter_09: 15 files

Chapter_10: 18 files

Chapter_11: 19 files

Chapter_12: 16 files

Chapter_13: 7 files

Chapter_14: 12 files

Chapter_15: 10 files

Small preview of the folder tree
Chapter_01/
  - lib/core/core.mli        (when path lines were present)
  - lib/core/core.ml
  - apps/cli/main.ml
  - dune
  - snippet_005.ml
  ... +46 more

Chapter_02/
  - snippet_001.ml
  - snippet_002.ml
  - snippet_003.ml
  - snippet_004.ml
  - snippet_005.ml
  ... +52 more

...

Chapter_15/
  - snippet_001.ml
  - snippet_002.ml
  - snippet_003.ml
  - snippet_004.ml
  - snippet_005.ml
  ... +5 more

How to use

Download the ZIP above and extract it.

If the project shows Dune stanzas and OPAM metadata in the chapter code, you can create a test workspace:

opam switch create . 5.2.1 -y

eval "$(opam env)"

opam install . --deps-only -y

dune build

When files are named snippet_###.ml, they’re independent examples or fragments. You can copy them into a scratch OCaml project or a chapter-specific Dune library/exe to compile and run.

Notes and edge cases

If a code block appeared before any chapter heading, I placed it in Chapter_00.

Some chapters mix OCaml with config, Dune, OPAM, or CI YAML. I kept those, since they’re part of the runnable setups described in the text.

In a few places the book shows partial snippets meant to illustrate an API or pattern rather than compile standalone. Those are still included as-is, with the snippet_###.ml naming.

If you want me to rename or regroup files in a specific way (for example, rebuild the chapter projects into one compilable per-chapter repo with dune-project and opam pinned per chapter), say the word and I’ll restructure it.
