1. Execute - ssh-keygen -t rsa -b 4096 -C “<triac email id>”
2. Get the key using - cat ~/.ssh/id_rsa.pub
3. Add the key in bitbucket => setings => personal settings => SSH keys
4. Then access git clone git@bitbucket.org:triac/fortherp.git
