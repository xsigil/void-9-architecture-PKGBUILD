# void-9-architecture-PKGBUILD

Arch Linux package build definition for **Void Architecture™ Sovereign Engine** (`void`).

## Installation

### Via makepkg

```bash
git clone [https://github.com/xsigil/void-9-architecture-PKGBUILD.git](https://github.com/xsigil/void-9-architecture-PKGBUILD.git)
cd void-9-architecture-PKGBUILD
makepkg -sric

```

## Quick Verification

# Verify binary is available
```bash
void help
```
# Scaffold an OCaml (Dune + Dream) sovereign stack (Default)
```bash
void scaffold my-app
```

# Scaffold a pure Go stack (Optional)
```bash
void scaffold --go my-go-app
```
