# FerMatter website

- Website and user guide: [fermatter.github.io](https://fermatter.github.io/).
- This repository contains generated public HTML, assets and synthetic sample ZIPs. Application sources and Git history remain in [k-onoue/FerMatter](https://github.com/k-onoue/FerMatter) (repository access required).
- Edit `site/` and `user-docs/` in the application repository. Its reviewed `main` builds publish here automatically using a website-only deploy key.
- `.github/workflows/pages.yml` deploys this repository's `main` with GitHub Pages. Change the workflow, this README and the license through a reviewed pull request; generated files are replaced by the next publication.
- Experimental Ubuntu packages and signed APT snapshots are release assets under `ubuntu-apt`; binaries and signing secrets stay out of Git. Pages verifies the pinned public key, signatures, checksums and archive paths before staging `/apt/`.
- `FERMATTER_APT_AVAILABLE=true` makes a missing APT release fail deployment after bootstrap. The release publisher sets it before requesting deployment; do not clear it to bypass a publication failure.
- The reviewed staging helper is maintained in `scripts/stage-apt-repository.py` in the application repository; copy updates here through a PR.
