# Makefile: tests unbound python module (please edit SCRIPT variable)
#
# Copyright (c) 2009, Zdenek Vasicek (vasicek AT fit.vutbr.cz)
#                     Marek Vavrusa  (xvavru00 AT stud.fit.vutbr.cz)
#
# This software is open source.
# 
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
# 
#    * Redistributions of source code must retain the above copyright notice,
#      this list of conditions and the following disclaimer.
# 
#    * Redistributions in binary form must reproduce the above copyright notice,
#      this list of conditions and the following disclaimer in the documentation
#      and/or other materials provided with the distribution.
# 
#    * Neither the name of the organization nor the names of its
#      contributors may be used to endorse or promote products derived from this
#      software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED
# TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
# PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE REGENTS OR CONTRIBUTORS BE
# LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
# CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
# SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
# INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
# CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
# ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
# POSSIBILITY OF SUCH DAMAGE.

SUEXEC  = sudo
UNBOUND = ../unbound
SCRIPT  = ./test-resip.conf

UNBOUND_OPTS = -dv -c $(SCRIPT)

.PHONY: test sudo suexec doc

all: test

$(UNBOUND):
	make -C ..

test: $(UNBOUND)
	$(UNBOUND) $(UNBOUND_OPTS)

sudo: $(UNBOUND)
	sudo $(UNBOUND) $(UNBOUND_OPTS)

suexec: $(UNBOUND)
	su -c "$(UNBOUND) $(UNBOUND_OPTS)"

doc:
	$(MAKE) -C doc html
