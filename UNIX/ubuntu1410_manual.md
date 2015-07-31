ubuntu1410構築手順

vagrantをインストール
略

virthalboxをインストール
略

ubuntu1410をadd ,そして　vagrantfileを編集
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu1410"
  config.vm.network :forwarded_port, guest:80, host:8080, id:"http"
  config.vm.network "private_network", ip: "192.168.33.11"
  config.vm.synced_folder "../share_with_vagrant", "/vagrant_data"
  config.vm.provider "virtualbox" do |vb
  vb.gui = true
  end

ネットにつながらないです。その理由は、ubuntuは自分設定したDNS名前解決できず。
修正します
vim /etc/resolv.conf
change 10.0.2.3 to 8.8.8.8

need to do at first place
* create my account
* make my account can sudo
* sudo apt-get install curl
* sudo apt-get install vim
* sudo apt-get install git
* sudo apt-get install zsh
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
which zsh
chsh  #自分のデフォルトshellを設定
sudo reboot

sudo apt-get install sublime-text


vimの設定に関して
http://catcher-in-the-tech.net/1063/
NERDTreeのインストール以外にも、おすすめのpluginがある。
tpope/vim-fugitve 
use Neobundle install this plugin.
make git more powerful, for example git blame
:Gblame will show that
