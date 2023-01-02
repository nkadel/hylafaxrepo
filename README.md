hylafaxrepo
==========-

Wrapper for SRPM building tools for hylafax+ 7.x.

Building hylafax+
===============

Ideally, install "mock" and use that to build for both RHEL 7 through
9 and Fedora 37. Run these commands at the top directory.

* make getsrc # Get source tarvalls for all SRPMs
* make cfgs # Create local .cfg configs for "mock".

* make repos # Creates local local yum repositories in $PWD/hylafaxrepo

* make # Make all distinct versions using "mock"

Building a compoenent, without "mock" and in the local working system,
can also be done for testing.

* make build

hylafax has strong dependencies on uucp and mgetty, nonly published for Fedora.

Installing Hylafax
=================

The relevant yum repository is built locally in hylafaxreepo. To enable the repository, use this:

* make repo

Then install the .repo file in /etc/yum.repos.d/ as directed. This
requires root privileges, which is why it's not automated.

Hylafax RPM Build Security
====================

There is a significant security risk with enabling yum repositories
for locally built components. Generating GPG signed packages and
ensuring that the compneents are in this build location are securely
and safely built is not addressed in this test setup.

		Nico Kadel-Garcia <nkadel@gmail.com>
