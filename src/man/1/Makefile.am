#########################################################################
#									#
# Script ID: src/man/1/Makefile.am					#
# Author: Copyright (C) 2018-2019  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# AutoMake script file to generate Bintray Debian Upload manual pages	#
# from source.								#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 15/10/2018	MG	1.0.1	Initial release.			#
# 23/09/2019	MG	1.0.2	Remove shebang.				#
#									#
#########################################################################


bin-deb-upl.sh.1: Makefile
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

bin-deb-upl.sh.1: $(srcdir)/bin-deb-upl.sh.1.man.in

man_MANS = bin-deb-upl.sh.1

EXTRA_DIST = $(srcdir)/bin-deb-upl.sh.1.man.in

CLEANFILES = *.tmp bin-deb-upl.sh.1

