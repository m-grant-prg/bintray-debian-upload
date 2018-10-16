#! /usr/bin/env bash
#########################################################################
#									#
# Script ID: src/prg/bash/Makefile.am					#
# Author: Copyright (C) 2018  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# AutoMake script file to generate bin-deb-upl.sh script from source.	#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 13/10/2018	MG	1.0.1	Initial release.			#
#									#
#########################################################################


bin-deb-upl.sh: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).in > $@.tmp
	mv $@.tmp $@
	chmod a+x $@
bin-deb-upl.sh: $(srcdir)/bin-deb-upl.sh.in


bin_SCRIPTS = bin-deb-upl.sh


EXTRA_DIST = $(srcdir)/bin-deb-upl.sh.in

CLEANFILES = *.tmp bin-deb-upl.sh

