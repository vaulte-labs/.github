# Security

Vaulte holds people's secrets, so a weakness in it matters more than any other bug. Thank you for
looking.

## Report privately

Open the repository's **Security** tab and choose **Report a vulnerability**. Only the maintainers
see the report. Please don't open a public issue, pull request or discussion about it.

Include what an attacker needs (a copy of the vault, a process running as the user, a peer on the
network, the relay), what they get, and the steps or a test that shows it. The commit you tested
and your macOS version and chip help.

We reply within a week, keep you told as we fix it, and credit you in the published advisory unless
you'd rather not be named.

## What counts

Anything that lets someone read or use a secret without the approval Vaulte promises, change the
vault without it, roll it back, or learn what is in it. That includes the hosted relay learning
anything beyond addresses, timing and sizes.

The threat model in [libvault's DESIGN.md](https://github.com/vaulte-labs/libvault/blob/main/DESIGN.md#threats)
says what each attacker should get. A gap between that table and what the code does is a
vulnerability, and so is a claim there marked **assumed** that turns out false. Root or a kernel
compromise while the vault is unlocked is out of scope, as the table says.

## Supported versions

Only the latest commit on `main`. There are no releases yet.

## Good-faith research

Test against your own vaults and devices. Don't access other people's data, and don't degrade the
hosted relay for others. Research done this way is welcome, and we won't pursue it.
