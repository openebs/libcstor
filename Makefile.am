# Copyright © 2020 The OpenEBS Authors
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at

# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

ACLOCAL_AMFLAGS= -I m4
AUTOMAKE_OPTIONS = foreign

SUBDIRS = src include

check-license:
	@echo ">> checking license header"
	licRes=$$(for file in $$(find . -type f -regex '.*\.sh\|.*\.c\|.*\.cc\|.*\.am\|.*\.h\|.*Docker.*' ! -path ./config.h) ; do \
	         awk 'NR<=5' $$file | grep -Eq "(Copyright|generated|GENERATED)" || echo $$file; \
	done); \
	if [ -n "$${licRes}" ]; then \
		echo "license header checking failed:"; echo "$${licRes}"; \
		exit 1; \
	fi
