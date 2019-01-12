# GCP
允许0.0.0.0/0通过端口流量9000

# VPS
- prepare
<pre><code>
sudo su
ufw disable
apt-get remove iptables
cd /etc/
mddir shadowsocks-r
cd shadowsocks-r
wget https://raw.githubusercontent.com/nakfc/SSR-config.json/master/config.json
</pre></code>
- docker
<pre><code>
wget -qO- get.docker.com | bash 
systemctl enable docker
docker pull teddysun/shadowsocks-r
docker run -d -p 9000:9000 -p 9000:9000/udp --name ssr -v /etc/shadowsocks-r:/etc/shadowsocks-r teddysun/shadowsocks-r
docker ps -l
docker restart ssr
</pre></code>
# SSR
