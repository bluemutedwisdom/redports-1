# redports scripts Makefile

TARGET=/usr/local/bin
FRONTENDFILES=rpaddcommit rparchivesvn rpclient rpcreateaccount rpqat
BACKENDFILES=rpcreatebuild rpmaintainbuild rptmpfsclean
PRTOOLFILES=rpfetchpr rpcommitpr rpwatchpr

all:
install: install-frontend install-backend install-prtools
deinstall: deinstall-frontend deinstall-backend deinstall-prtools

# install
install-frontend:
.for file in ${FRONTENDFILES}
	install -o root -g wheel -m 0555 ${file} ${TARGET}
.endfor

install-backend:
.for file in ${BACKENDFILES}
	install -o root -g wheel -m 0555 ${file} ${TARGET}
.endfor
	install -o root -g wheel -m 0555 rpmaintainbuild.rc /usr/local/etc/rc.d/rpmaintainbuild

install-prtools:
.for file in ${PRTOOLFILES}
	install -o root -g wheel -m 0555 ${file} ${TARGET}
.endfor


# deinstall
deinstall-frontend:
.for file in ${FRONTENDFILES}
	rm -f ${TARGET}/${file}
.endfor

deinstall-backend:
.for file in ${BACKENDFILES}
	rm -f ${TARGET}/${file}
.endfor
	rm -f /usr/local/etc/rc.d/rpmaintainbuild

deinstall-prtools:
.for file in ${PRTOOLFILES}
	rm -f ${TARGET}/${file}
.endfor
