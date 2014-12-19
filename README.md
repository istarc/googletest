googletest
==========

 Unofficial googletest Clone https://code.google.com/p/googletest/

Created by:

	# Import Svn Repository
	git svn clone --username=googletest-read-only --prefix=upstream/ \
	              -s http://googletest.googlecode.com/svn googletest

	# Import Tags
	cd googletest
	for tag in `git branch -r | grep "upstream/tags/" | sed 's/upstream\/tags\///'`; do
	  git tag -a -m"Converting SVN tags" $tag refs/remotes/upstream/tags/$tag
	done

	# Push to Origin
	git remote add origin git@github.com:istarc/googletest.git
	git fetch --all
	git merge origin/master # Merge .gitignore and README.md
	git push --all origin
	git push --tags origin

Clone (no warranties):

    git clone https://github.com/istarc/googletest.git

Update:

    git svn rebase

Checkout a tag:

    git tag -l
    git checkout release-1.7.0
