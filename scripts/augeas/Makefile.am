
EXTRA_DIST = gen-nutupsconf-aug.py nutupsconf.aug.tpl \
	README tests/test_nut.aug

# only call the script to generate Augeas ups.conf lens upon "make dist",
# and if Python is present
dist-hook:
	@if python -c "import re,glob,codecs"; then \
		echo "Regenerating Augeas ups.conf lens."; \
		$(distdir)/gen-nutupsconf-aug.py $(distdir)/; \
	else \
		echo "----------------------------------------------------------------------"; \
		echo "Warning: Python is not available."; \
		echo "Skipping Augeas ups.conf lens regeneration."; \
		echo "----------------------------------------------------------------------"; \
	fi

if WITH_AUGLENS
# Now "make install" should cover delivery of Augeas lenses...
# The "auglensdir" value should be set up by configure
# The *.aug files are generated by rule above or by autogen.sh and/or configure
 auglens_DATA = \
    nuthostsconf.aug  nutupsconf.aug   nutupsdusers.aug   nutupsschedconf.aug \
    nutnutconf.aug    nutupsdconf.aug  nutupsmonconf.aug  nutupssetconf.aug
endif
