GitHub action for building Isabelle packages
============================================

This action builds an [Isabelle][isabelle] session in quick-and-dirty
mode with PDF document generation and uploads the generated PDF
document as a GitHub Actions artifact.

[isabelle]:
    https://isabelle.in.tum.de/
    "Isabelle"


Usage
-----

This action is intended to be run on `ubuntu-latest` in the
`texlive/texlive:latest` container. It yields no outputs but takes the
following inputs:

  * **`session-name`** – Name of the session *(required)*

  * **`chapter-name`** – Name of the chapter the session belongs to
    *(required)*

  * **`source-path`** – Path to the source directory of the session
    relative to `$GITHUB_WORKSPACE` *(not required; defaults to `.`)*

  * **`isabelle-version`** – Isabelle version to use for building
    *(required)*

  * **`github-sessions`** – Space-separated list of needed Isabelle
    sessions from other GitHub repositories, each specified as
    `⟨user-name⟩/⟨repository⟩:⟨path⟩` *(not required; defaults to the
    empty list)*


Limitations
-----------

  * Isabelle versions older than 2012 cannot be used, as their websites
    have a structure not compatible with this action. It is not
    guaranteed that newer Isabelle versions except the current one can
    be used, as their interfaces may be incompatible with this action.
