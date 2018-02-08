FROM wordpress

RUN apt-get update && apt-get install -y git vim ssh expect

# RUN mkdir /home/.ssh
# ADD .ssh/id_rsa.pub /home/.ssh/id_rsa.pub
# ADD .ssh/id_rsa /home/.ssh/id_rsa
# ADD .ssh/known_hosts /home/.ssh/known_hosts
#
# ADD .ssh /home/.ssh

# RUN  echo "    IdentityFile ~/.ssh/id_rsa" >> /etc/ssh/ssh_config

# RUN chmod 700 /home/.ssh/id_rsa
# RUN eval "$(ssh-agent -s)" && ssh-add /home/.ssh/id_rsa

# ADD .ssh/id_rsa /tmp/
# RUN ssh-agent /tmp
# RUN rm /tmp/id_rsa

RUN mkdir ~/.ssh
RUN echo 'IdentityFile ~/.ssh/id_rsa' > ~/.ssh/config
RUN chmod 700 ~/.ssh/config
RUN eval "$(ssh-agent -s)" && echo '' | ssh-add ~/.ssh/config
# RUN set timeout 360
# RUN spawn ssh-add ~/.ssh/config
# RUN expect "Enter passphrase for /root/.ssh/config:" { send "\r" }

# RUN echo '\r' | ssh-add ~/.ssh/config

RUN cd .. && git clone git@github.com:effortless-technologies/elt-marketplace-wp.git
