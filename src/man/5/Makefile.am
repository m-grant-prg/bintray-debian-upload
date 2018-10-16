#! /usr/bin/env bash
#########################################################################
#									#
# Script ID: src/man/5/Makefile.am					#
# Author: Copyright (C) 2018  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# AutoMake script file to generate bintray-debian-upload  manual pages	#
# from source.								#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 16/10/2018	MG	1.0.1	Initial release.			#
#									#
#########################################################################


bintray.conf.5 bintray-debian-upload.conf.5: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	$(edit) $(srcdir)/$(@F).man.in > $@.tmp
	targfile=$(@F);	\
	if [[ $$targfile == *"."* ]]; then \
		if [[ $${targfile##*.} == "" ]]; then \
			echo "Source file suffix used as section but empty."; \
			exit 1; \
		else \
			section=$${targfile##*.}; \
		fi; \
	else \
		echo "Source file suffix used as section but no dot & empty."; \
		exit 1; \
	fi; \
	txt2manwrap $(@F) $$section "Bintray Debian Upload Manual" \
		$@.tmp $@
	rm -f $@.tmp
bintray.conf.5: $(srcdir)/bintray.conf.5.man.in
bintray-debian-upload.conf.5: $(srcdir)/bintray-debian-upload.conf.5.man.in

man_MANS = bintray.conf.5 bintray-debian-upload.conf.5

EXTRA_DIST = $(srcdir)/bintray.conf.5.man.in \
	$(srcdir)/bintray-debian-upload.conf.5.man.in

CLEANFILES = *.tmp bintray.conf.5 bintray-debian-upload.conf.5

