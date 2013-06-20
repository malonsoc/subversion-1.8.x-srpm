Subversion 1.8.x SRPM building tools
=======
This github repo includes tools for building subversion-1.7.9
RPM's. It is based on the Fedora 17 subversion-1.7.2 package, and
includes tweaks merged from Repoforge's older subversion-1.6.x
packages for compilation on multiple versions of RHEL or Fedora.

There is a new component, "mod_dondothat" that. This is packaged
with mod_dav_svn, and provides limitations on server-burdensome
operations such as checking out entire repository trees.

There is a new package added by me, "subversion-tools", which holds
the other packages in /usr/bin/svn-tools which are now built and
installed along with mod_dontdothat. Unfortunately, the add-on scripts
are now merged with built binary components, so the documentation and
list of add-on server scripts are now in
/usr/share/doc/subversion-toos-*/tools-doc to distinguish them as
documentation.

The API documentation used to be built as part of subversion-devel.
Fedora separated this out into subversion-api-docs, for good reasons,
so that needs to be built separately.

The bash-completion utility was installed rather oddly: that has been
cleaned up.

RHEL 5 is no longer supported. Backporting Python 2.6 is too awkward.

RHEL 4 is no longer supported. The tool chain and the necessary build
components, such as Python 2.6, sqlite, swig, , have gotten
unreasonable to maintain and build locally.

The following components are not compatible with older RHEL releases,
such as RHEL 5 or RHEl 4.

        psvn - No longer compatible with older Emacs or Xemacs.
		Not included in subversion package for old OS.
	subversion-kde - requires KDE4 Required rewrite of
		dependencies for RPM building. subversion-kde is still
		built, but as placeholder.
	SQLite - Modern SQLite or "sqlite-amalgamation" required for
		compilation.  Use new SQLite tarball as needed.

	perl-devel - Spurious dependency for compilation, does not
		exist on RHEL 5.