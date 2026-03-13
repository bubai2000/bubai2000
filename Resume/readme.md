### Package requirements (Estimated):
---
* texlive-basic
* texlive-bin
* texlive-fontsrecommended
* texlive-fontsextra
* texlive-langenglish
* texlive-latex
* texlive-latexextra
* texlive-latexrecommended
* texlive-mathscience
* texlive-pictures
* texlive-xetex

### Refresh font cache
1. Check TEXMF distribution tree directory:
    ```bash
    kpsewhich -var-value=TEXMFDIST
    ```
2. Add font directory to fontcache config file:
    * Location for Global Font Cache Config File: `/etc/fonts/local.conf`
    * Location for User Specific File: `~/.config/fontconfig/fonts.conf`
    Config:
        ```xml
        <?xml version="1.0"?>
        <!DOCTYPE fontconfig SYSTEM "fonts.dtd">
        <fontconfig>
        <dir>/usr/share/texmf-dist/fonts/opentype</dir>
        <dir>/usr/share/texmf-dist/fonts/truetype</dir>
        </fontconfig>
        ```
    (Note: replace `/usr/share/texmf-dist` with output of `kpsewhich -var-value=TEXMFDIST`)
3. Refresh font cache:
    ```bash
    fc-cache -fv
    ```