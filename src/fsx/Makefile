#
# Copyright (c) 2009 Apple Inc. All rights reserved.
#
# @APPLE_LICENSE_HEADER_START@
# 
# This file contains Original Code and/or Modifications of Original Code
# as defined in and that are subject to the Apple Public Source License
# Version 2.0 (the 'License'). You may not use this file except in
# compliance with the License. Please obtain a copy of the License at
# http://www.opensource.apple.com/apsl/ and read it before using this
# file.
# 
# The Original Code and all software distributed under the License are
# distributed on an 'AS IS' basis, WITHOUT WARRANTY OF ANY KIND, EITHER
# EXPRESS OR IMPLIED, AND APPLE HEREBY DISCLAIMS ALL SUCH WARRANTIES,
# INCLUDING WITHOUT LIMITATION, ANY WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE, QUIET ENJOYMENT OR NON-INFRINGEMENT.
# Please see the License for the specific language governing rights and
# limitations under the License.
# 
# @APPLE_LICENSE_HEADER_END@
#

ARCHS := ppc i386 x86_64
INTERNAL_FRAMEWORKS := /AppleInternal/Library/Frameworks
CFLAGS := $(ARCHS:%=-arch %) -Wall -O3

ifeq ($(wildcard $(INTERNAL_FRAMEWORKS)), $(INTERNAL_FRAMEWORKS))
CPPFLAGS += -DXILOG
CFLAGS += -F/AppleInternal/Library/Frameworks
LIBS += -framework XILog
endif

.PHONY: clean

fsx:
	$(CC) $(CFLAGS) $(CPPFLAGS) -o $@ fsx.c $(LIBS)

clean:
	-rm -f *.o fsx

