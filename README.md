node rpm specfile
=================
Node.js does not come with RPMs for CentOS 6.3 and Fedora 18.  Fedora 19 already has node packages listed as part of their project but the number of depenancies make it difficult to install well on Fedora 18.  Here are instructions to build node rpms from source.

Steps to build
--------------------------------------------------------
1. sudo yum groupinstall 'Development Tools'
2. sudo yum install openssl-devel python rpmdevtools
3. rpmdev-setuptree
4. wget -P ~/rpmbuild/SPECS https://raw.github.com/brockers/node-rpm-spec/master/nodejs.spec
5. spectools -C ~/rpmbuild/SOURCES/ -g ~/rpmbuild/SPECS/nodejs.spec
6. rpmbuild -ba ~/rpmbuild/SPECS/nodejs.spec
7. rpmdev-wipetree
