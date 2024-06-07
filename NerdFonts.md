# [[NerdFonts]]

- https://github.com/ryanoasis/nerd-fonts/releases/tag/v3.2.1

### Install Nerd Font - Debian BASH 

```bash
#!/usr/bin/env bash

function install_nerd_font {
	local FONT_DEST="$HOME/.local/share/fonts"
	# local FONT_DEST="."
	local NERD_FONT_VERSION="3.2.1"
	local NERD_FONT_NAME="${1}"
	local OLD_PWD=$(pwd)

	mkdir -p $FONT_DEST
	cd $FONT_DEST

    local DOWNLOAD_URL="https://github.com/ryanoasis/nerd-fonts/releases/download/v${NERD_FONT_VERSION}/${NERD_FONT_NAME}.zip"
	echo $DOWNLOAD_URL
    curl -sSfLO "${DOWNLOAD_URL}"
	unzip "${NERD_FONT_NAME}.zip"
    rm -rf "${NERD_FONT_NAME}.zip"
    rm LICENSE.txt README.md 
	
	cd $OLD_PWD
}
install_nerd_font "${@}"
```

