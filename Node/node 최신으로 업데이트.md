# node 최신으로 업데이트
## 방법1
	sudo npm cache clean -f
	sudo npm install -g n
	sudo n stable
	sudo ln -sf /usr/local/n/versions/node/6.0.0/bin/node /usr/bin/node

## 방법2
	sudo brew uninstall node
	brew update
	brew upgrade
	brew cleanup
	brew install node
	sudo chown -R myusername /usr/local
	brew link --overwrite node
	brew postinstall node


