# Copyright (c) 2012-2016 Codenvy, S.A.
# All rights reserved. This program and the accompanying materials
# are made available under the terms of the Eclipse Public License v1.0
# which accompanies this distribution, and is available at
# http://www.eclipse.org/legal/epl-v10.html
# Contributors:
# Codenvy, S.A. - initial API and implementation

FROM codenvy/ubuntu_jre
RUN sudo add-apt-repository -y ppa:ubuntu-toolchain-r/test && \
    sudo apt-get update && \
    sudo apt-get install g++-6 gcc-6 make gdb gdbserver automake libtool cmake vim tmux valgrind -y && \
    (curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -) && \
    sudo apt-get install -y nodejs && \
    sudo apt-get clean && \
    sudo apt-get -y autoremove && \
    sudo rm -rf /var/lib/apt/lists/* && \
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 1 --slave /usr/bin/g++ g++ /usr/bin/g++-6 && \
    for i in bashrc tmux.conf vimrc gitconfig valgrindrc; do \
        curl https://raw.githubusercontent.com/friedmag/config/master/$i >/home/user/.$i; \
    done

WORKDIR /projects

CMD tail -f /dev/null
