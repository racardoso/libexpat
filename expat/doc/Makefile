# Copyright (C) Sebastian Pipping <sebastian@pipping.org>
# Licensed under MIT/X License

DOCBOOK_TO_MAN := $(shell command -v docbook2x-man 2> /dev/null)

.PHONY: all
all: check xmlwf.1

check:
ifndef DOCBOOK_TO_MAN
DOCBOOK_TO_MAN := $(shell command -v db2x_docbook2man 2> /dev/null)
ifndef DOCBOOK_TO_MAN
DOCBOOK_TO_MAN := $(shell command -v docbook-to-man 2> /dev/null)
ifndef DOCBOOK_TO_MAN
$(error "docbook2x is not installed.")
endif
endif
endif

xmlwf.1: XMLWF.1
	cp $< $@

XMLWF.1: xmlwf.xml
	$(DOCBOOK_TO_MAN) xmlwf.xml

.PHONY: clean
clean:
	$(RM) xmlwf.1 XMLWF.1
