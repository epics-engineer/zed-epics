# EPICS for Zed

This is an unofficial Zed extension for EPICS and StreamDevice files.

It uses the split Tree-sitter grammars maintained by [Rémi NICOLE (`minijackson`)](https://github.com/minijackson).

## Supported files

| Zed language | Grammar | Files | Upstream grammar |
| --- | --- | --- | --- |
| EPICS Command | `epics_cmd` | `.cmd` | https://github.com/minijackson/tree-sitter-epics-cmd |
| EPICS Database | `epics_db` | `.db`, `.dbd`, `.template`, `.vdb` | https://github.com/minijackson/tree-sitter-epics-db |
| EPICS MSI Substitution | `epics_msi_substitution` | `.sub`, `.subs`, `.substitutions` | https://github.com/minijackson/tree-sitter-epics-msi-substitution |
| EPICS MSI Template | `epics_msi_template` | macro injections | https://github.com/minijackson/tree-sitter-epics-msi-template |
| EPICS SNL | `snl` | `.st`, `.stt` | https://github.com/minijackson/tree-sitter-snl |
| StreamDevice Protocol | `streamdevice_proto` | manual selection by default | https://github.com/minijackson/tree-sitter-streamdevice-proto |

StreamDevice protocol files normally use `.proto`, but Protocol Buffers uses the same suffix. This extension does not take over all `.proto` files. Pick `StreamDevice Protocol` from Zed's language selector, or add a file type override in projects where `.proto` means StreamDevice:

```json
{
  "file_types": {
    "StreamDevice Protocol": ["proto"]
  }
}
```

## Install as a dev extension

Clone the repository:

```sh
git clone https://github.com/epics-engineer/zed-epics.git
```

In Zed, run `zed: install dev extension` from the command palette and select the cloned `zed-epics` directory.

Zed compiles the Tree-sitter grammars during installation. If installation fails, run `zed: open log` and check the grammar checkout or build error. For local development, Zed expects Rust to be installed through `rustup`.

## Pinned grammars

The extension pins the latest grammar releases that were available when this package was created:

| Grammar | Release tag |
| --- | --- |
| `epics_cmd` | `v0.1.5` |
| `epics_db` | `v0.2.0` |
| `epics_msi_substitution` | `v0.3.0` |
| `epics_msi_template` | `v0.1.2` |
| `snl` | `v0.2.1` |
| `streamdevice_proto` | `v0.2.1` |

The manifest pins the exact commit for each release because Zed's dev extension checkout can fail on annotated tags.


