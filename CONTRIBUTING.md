# Contributing

Thank you for helping. Vaulte guards people's secrets, so changes are held to a high bar, and these
notes are about clearing it on the first try.

**Found a vulnerability?** Don't open an issue. Follow [SECURITY.md](SECURITY.md).

## Before you write code

Open an issue first for anything bigger than a small, obvious fix. Say what a person or agent can't
do today, or what goes wrong, and how you'd change it. Changes to keys, the vault format, the
broker's policy or sync are decided in the issue before any code is written, because they change
the threat model.

Never paste a secret, a vault file, recovery words or a session token into an issue or pull request,
even a test one.

## Getting set up

The repositories build against each other by relative path, so clone them side by side:

```sh
mkdir vaulte && cd vaulte
git clone https://github.com/vaulte-labs/libvault
git clone https://github.com/vaulte-labs/sdk   # needs ../libvault
git clone https://github.com/vaulte-labs/ts    # needs ../sdk and ../libvault
```

Each repository pins its toolchain in `mise.toml`. With [mise](https://mise.jdx.dev), run
`mise install` in it. On a Mac, the build compiles the Secure Enclave bridge with `swiftc`, so it
needs Xcode 26 or its Command Line Tools. Each README has the rest.

## Making a change

- **Run `scripts/check.sh` before every commit.** It formats, lints with Clippy's pedantic set as
  errors, runs every test, and enforces the rules that used to be advice: `unsafe` only where it is
  contained, no source file over 500 lines, no internal module exposed. A pull request that fails it
  won't be reviewed.
- **Test what a person would see.** A test drives the public API, or the real broker, the way an
  interface would, and fails if the behavior breaks. A change to the security code should survive
  `scripts/mutants.sh` in libvault, and a new parser of untrusted input gets a fuzz target.
- **Keep claims honest.** DESIGN.md tags each claim **tested**, **documented** or **assumed**. If your
  change makes one true or false, update the tag.
- **One change per pull request**, with commits that each build and pass.
- **Commit messages** say what someone can now do, or what no longer goes wrong, in the imperative:
  "Let an app list logins for the system's autofill", not "Update autofill.rs".

## Licensing

Your contribution is licensed under the [contributor license agreement](CLA.md). You keep your
copyright, and Vaulte Labs can offer the code under both the AGPL-3.0 and a commercial license,
which is what pays for the project. The pull request template asks you to agree to it.

Everyone taking part follows the [code of conduct](CODE_OF_CONDUCT.md).
