#########################################################################
#									#
# Script ID: src/conf/etc/Makefile.am					#
# Author: Copyright (C) 2018-2019  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# AutoMake script file to install the bintray debian upload config	#
# files.								#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 16/10/2018	MG	1.0.1	Initial release.			#
# 23/09/2019	MG	1.0.2	Remove shebang.				#
#									#
#########################################################################


confdir = $(sysconfdir)

bintray-debian-upload.conf: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).in > $@.tmp
	mv $@.tmp $@
bintray-debian-upload.conf: $(srcdir)/bintray-debian-upload.conf.in

conf_DATA = bintray-debian-upload.conf

EXTRA_DIST = $(srcdir)/bintray-debian-upload.conf.in

CLEANFILES = *.tmp bintray-debian-upload.conf

