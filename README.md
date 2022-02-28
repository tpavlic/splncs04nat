# splncs04nat
natbib compatible splncs04.bst (Springer LNCS) BibTeX Style File built using a docstrip with the conventional merlin.mbs master file.

This repository includes both a docstrip batch job (`splncs04nat.dbj`) and
a BibTeX style file (`splncs04nat.bst`) that is built directly from it.
The resulting `splncs04nat.bst` emulates the `splncs04.bst` from Springer;
however, `splncs04nat.bst` is `natbib` compatible.

## Generation of these files

The docstrip batch job `splncs04nat.dbj` was generated interactively
using `makebst` with:

```bash
latex makebst
```

where the standard master file `merlin.mbs` was used. After selection
options compatible with `splncs04.bst`, the docstrip batch job
`splncs04nat.dbj` was built. Then:

```bash
latex splncs04nat.dbj
```

was used to trigger docstrip to filter `merlin.mbs` appropriately to
generate the desired `splncs04nat.bst.`

## Use of these files

Use these lines in the preamble:

```latex
\usepackage[numbers,sort&compress]{natbib}
\bibliographystyle{splncs04nat}
```

and use this line before the `\end{document}`:

```latex
\bibliography{yourbib}
```

where `yourbib` should be replaced with your BibTeX bibliography
database. Then, within the document, `natbib` macros can be used, as in:

```latex
\cite{PP14}
\citep{GH04}
\citet{SK86}
```

The latter macros, ```\citet```, will not properly include the author
names if the standard `splncs04.bst` is used.
