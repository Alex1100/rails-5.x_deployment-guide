# STEPS TO DEPLOY RAILS APP WITH AWS EC2 Redhat/Amazon Linux Container Instance
<hr/>
<img width="100" height="100" src="https://pbs.twimg.com/profile_images/476766169349636096/xUHXk6zu.png" />
<img width="200" height="150" src="https://d7umqicpi7263.cloudfront.net/img/product/40753dc3-0182-458f-9268-213115224d8d/c10dfd79-1fb7-4a73-8290-43736e40b00c.png" />

<ol>
    <li>
        <p>Launch New EC2 Instance in AWS console</p>
    <li>
        <p>Define Security Groups</p>
        <p>Include public ip addr as custom tcp rule for security group</p>
    </li>
    <li>
        <p>Skip all steps and Launch</p>
    </li>
    <li>
        <p>Download New Pem file or use previous pem file</p>
    </li>
    <li>
        <p>chmod 400 Pem file</p>
    </li>
    <li>
        <p>ssh into machine by running <code>ssh -i ~/directory-of-pem-file/pemfile ec2user@public ip address of launched instance</code></p>
    </li>
    <li>
        <p>Prepare the Newly Launched Machine's System</p>
    </li>
    <li>
        <p>run <code>sudo yum install -y curl gpg gcc gcc-c++ make</code></p>
    </li>
    <li>
        <p>run <code>sudo gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3</code></p>
    </li>
    <li>
        <p>run <code>curl -sSL https://get.rvm.io | sudo bash -s stable</code></p>
    </li>
    <li>
        <p>run <code>sudo usermod -a -G rvm `whoami`</code></p>
    </li>
    <li>
        <p>run <code>if sudo grep -q secure_path /etc/sudoers; then sudo sh -c "echo export rvmsudo_secure_path=1 >> /etc/profile.d/rvm_secure_path.sh" && echo Environment variable installed; fi</code></p>
    </li>
    <li>
        <h3>To install latest version of Ruby</h3>
        <p>run <code>rvm install ruby</code></p>
        <p>run <code>rvm --default use ruby</code></p>
    </li>
    <li>
        <h3>To install a specific version of Ruby</h3>
        <p>run <code>rvm install ruby-X.X.X</code></p>
        <p>run <code>rvm --default use ruby-X.X.X</code></p>
    </li>
    <li>
        <h3>Install Bundler</h3>
        <p>run <code>gem install bundler --no-rdoc --no-ri</code></p>
    </li>
    <li>
        <h3>For Red Hat, CentOS, Fedora, Amazon Linux, Scientific Linux</h3>
        <p>run <code>sudo yum install -y epel-release</code></p>
    </li>
    <li>
        <h3>For Node LTS version</h3>
        <p>run <code>curl --silent --location https://rpm.nodesource.com/setup_8.x | sudo bash -</code></p>
        <br/>
        <h3>For Node Unstable Latest</h3>
        <p>run <code>curl --silent --location https://rpm.nodesource.com/setup_9.x | sudo bash -</code></p>
    </li>
    <li>
        <p>run <code>sudo yum install gcc-c++ make</code></p>
    </li>
    <li>
        <p>run <code>sudo yum install -y --enablerepo=epel nodejs npm</code></p>
    </li>
    <li>
        <h3>To Install Yarn For CentOS, Fedora, AWS Linux, Redhat, Redhat Enterprise Linux</h3>
        <p>run 
            <code>
                sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
            </code>
        </p>
    </li>
    <li>
        <p>run <code>sudo yum install yarn</code></p>
    </li>
    <li>
        <h3>Installing Git</h3>
        <p>run <code>sudo yum upgrade</code></p>
        <p>run <code>sudo yum instal git</code></p>
    </li>
    <li>
        <h3>Clone Git Repo to the SSH'ed Machine</h3>
        <p>run <code>git clone __cloned_repo_url__</code></p>
    </li>
    <li>
        <p>run <code>cd __name_of_cloned_repo__</code></p>
        <p>run <code>bundle install</code></p>
    </li>
    <li>
        <p>run <code>bundle update</code></p>
    </li>
    <li>
        <p>run <code>npm install || yarn instal</code></p>
    </li>
    <li>
        <p>Add ENV VARS via VIM</p>
    </li>
    <li>
        <h3>To test server and code</h3>
        <p>run <code>bundle exec ./bin/webpack</code>
        <p>run <code>rails s</code></p>
    </li>
    <li>
        <h3>To keep detached screen running forever while running the server</h3>
        <p>run <code>bundle exec ./bin/webpack</code></p>
        <p>run <code>screen rails s</code></p>
        <p>run <code>ctrl + A + D</code> to keep screen running but detach yourself from it</p>
        <p>run <code>screen -r</code> to view all running screen instance</p>
    </li>
</ol>
