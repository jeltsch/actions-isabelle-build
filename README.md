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

  * **`isabelle-mirror`** – Mirror of the Isabelle website from which to
    obtain the Isabelle software *(required)*

  * **`github-sessions`** – Space-separated list of needed Isabelle
    sessions from other GitHub repositories, each specified as
    `⟨user-name⟩/⟨repository⟩:⟨path⟩` *(not required; defaults to the
    empty list)*


Limitations
-----------

  * Isabelle versions before the current one are not provided via the
    current Isabelle website and therefore cannot be used out of the
    box. To use an older Isabelle version, use an archive of the
    corresponding older website as the mirror by appending
    `website-Isabelle⟨isabelle-version⟩/` to the mirror URL you would
    otherwise use. This should work with Isabelle versions back until
    2012 (including). That said, it is not guaranteed that you will be
    able to use a particular older Isabelle version, as its interface
    may be incompatible with this action.
