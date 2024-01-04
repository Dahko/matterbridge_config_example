Sample matterbridge config for forwarding WhatsApp group chats to Telegram with translation.


Some setup hints
====
```
sudo apt install golang-go
go install -tags nomsteams,whatsappmulti github.com/42wim/matterbridge@master
cp ~/go/bin/matterbridge /usr/bin/matterbridge
sudo adduser --system --no-create-home --group matterbridge
sudo mkdir /etc/matterbridge
# put your configs here ^^^
sudo chgrp -R matterbridge /etc/matterbridge/
sudo chmod g+w -R /etc/matterbridge/
sudo chmod o-r -R /etc/matterbridge/
sudo systemctl enable matterbridge
sudo systemctl start matterbridge
sudo journalctl -u matterbridge # check that it works

# For translation
sudo apt install translate-shell
go install github.com/d5/tengo/cmd/tengo@latest
sudo cp ~/go/bin/tengo /usr/bin/
```
