# Stable Releases

Our stable releases are the official release of the OpenSceneGraph to be used by new users and developer releasing final applications based that use the OpenSceneGraph.  We make major stable releases once to twice a year, such as 3.0, and minor stable releases to the stable release as necessary such as the 3.0.1 which fixed bugs that came to light after the first stable release in the series.  The versioning for stable release is major.minor.patch where the minor release is even number signifying that it's stable release.

Link OpenSceneGraph-3.6.5 release download
Source Code:
Github tag for 3.6.5:https://github.com/openscenegraph/OpenSceneGraph/tree/OpenSceneGraph-3.6.5
git clone --branch OpenSceneGraph-3.6.5 https://github.com/openscenegraph/OpenSceneGraph.git
Binaries :
Windows Binaries provided by OBJEXX Engineering

#Code Repositories
OpenSceneGraph Github Repository:
http://github.com/openscenegraph/osg

Requisits
git, obviously :

on Windows :
command line with msysgit
explorer integration with TortoiseGit
on Mac :
command line git installer
gitk : comes in with git and is a graphical local repository browser
[http://gitx.frim.nl/GitX ]
on Linux
git : command line : sudo apt-get install git-core
gitk : graphical local repository browser : sudo apt-get install gitk
git-gui : A Tcl/Tk based graphical user interface to Git sudo apt-get install git-gui
Background reading on git
Pro Git Book or Git Community Book is a good start ! But you might be more interested in the Git - SVN Crash Course : git explained to svn users.

Also have a look at Why git is better than X

Workflow
Read-Only
This workflow is intended for users who need to stay on top of OpenSceneGraph activity but do not intend to modify it for they own need nor contribute some enhancements or bug correction back.

Initial checkout

~ $ git clone https://github.com/openscenegraph/OpenSceneGraph.git
Update

~/OpenSceneGraph $ git pull
Contributor
When planning to contribute to OpenSceneGraph you need to record your changes so they can be pulled into the upstream by the maintainer. This is largely inspired from Michael Norton's blog entry Doc On Dev : 'Contributing to a project you find on GitHub'

You will need a GitHub account

1. Fork the OpenSceneGraph project

Login to github. Go to http://github.com/openscenegraph/OpenSceneGraph's git mirror project



To create a fork, press the "fork" button on the project's page.

When the fork is complete, you will have a copy of the project in your repositories listing.



2. Clone your project

Now back on your computer you need to clone your fork. Make sure you use the “Your Clone URL” and not the “Public Clone URL”. You want to be able to push changes back to your own repository.

~ $ git clone git@github.com:[your-github-account]/OpenSceneGraph.git
Once the clone is complete your repo will have a remote named “origin” that points to your fork on github. You will use "origin" for your own regular activities.

~/OpenSceneGraph (master)$ git remote -v 
origin git@github.com:[your-github-account]/osg.git (fetch) 
origin git@github.com:[your-github-account]/OpenSceneGraph.git (push)
3. LINK YOUR REPOSITORY TO THE UPSTREAM
upstream
repository that you forked
To keep track of the modifications committed to the 'upstream' branch of the project you need to add a remote branch to your local repository

~/OpenSceneGraph (master)$ git remote add upstream git://github.com/openscenegraph/OpenSceneGraph.git
You should now have another remote :

~/OpenSceneGraph (master)$ git remote -v
origin git@github.com:[your-github-account]/OpenSceneGraph.git (fetch)
origin git@github.com:[your-github-account]/OpenSceneGraph.git (push)
upstream git://github.com/openscenegraph/OpenSceneGraph.git (fetch)
upstream git://github.com/openscenegraph/OpenSceneGraph.git (push)
4. CREATE A BRANCH CONTAINING YOUR CONTRIBUTION
First step is to create a branch to make your modifications. Lets call it topic :

~/OpenSceneGraph (master)$ (master)> git checkout -b topic
Switched to a new branch 'topic'

~/OpenSceneGraph (topic)$ git branch
master
* topic
Now make your modifications to the project and commit them to your topic branch.

5. KEEP YOUR FORK UP-TO-DATE
Forking a repository is the recommended way of contributing to a github project. Alas it doesn't get updated with the latest commits from the forked repository.

The upstream remote we added in the previous topic will help you update your repository with those latest changes by pulling and then merging in them in as so :

~/OpenSceneGraph (master)$ git pull upstream master
Now your local upstream/master should contain all the new commits. You can merge them to your master branch.

~/OpenSceneGraph (master)$ git merge upstream/master
6. KEEP YOUR CONTRIBUTIONS UP-TO-DATE
When updating your repository with the upstream's modifications it is likely that your topic branch will need to integrate those changes too. This is called rebasing. This will modify your topic branch commits (yes, it will create some new commits) to make the topic branch start from the latest commits in the upstream repository.

~/OpenSceneGraph (topic)$ git rebase master
7. SUBMITTING YOUR CONTRIBUTION
See submissions page

# Dependencies
 Print  EmailCategory: Third Party Published: 07 May 2012 Written by Jordi Torres Hits: 175851
The OpenSceneGraph has range of dependencies, listed at the bottom of this page, most of which are optional and only required if you want to load a specific type of data. The OpenSceneGraph CMake based build system can automatically detect what dependencies you have installed and enable/disable the build of various modules according to what is available. Under Windows and Debian linux pre built binary packages available, using these can make your life a little easier.

## Windows prebuilt dependency packages

VisualStudio 2017
The following two packages are compiled with VisualStudio 2017 RTM (VC14) for 64bit only (v141 platform toolset). If you need 32bit (x86), please use this package. Please ensure you have the correct Visual Studio version installed. You can use the ENV variable OSG_3RDPARTY_DIR to auto configure CMake. Package details, content list and sources are available here
Small package for 64 bit https://download.osgvisual.org/3rdParty_VS2017_v141_x64_V11_small.7z - Last Update: V11 on 2017/03/22
Full package for 64 bit https://download.osgvisual.org/3rdParty_VS2017_v141_x64_V11_full.7z - Last Update: V11 on 2017/04/08
VisualStudio 2015
There is no prebuilt package at the moment but depending on which dependencies you need you could compile them yourself using the following CMake scripts https://github.com/bjornblissing/osg-3rdparty-cmake . (Updated 2016/2/22)
VisualStudio 2013 Update 5 (VC12)
The following two packages are compiled with VisualStudio 2013 RTM (VC12) for 64bit only (v120 platform toolset). If you need 32bit (x86), please use this package. Please ensure you have the correct Visual Studio version installed. You can use the ENV variable OSG_3RDPARTY_DIR to auto configure CMake. Package details, content list and sources are available here
Small package for 64 bit https://download.osgvisual.org/3rdParty_VS2013.5_v120_x64_V10_small.7z - Last Update: V10 on 2016/10/22
Full package for 64 bit https://download.osgvisual.org/3rdParty_VS2013.5_v120_x64_V10_full.7z - Last Update: V10 on 2016/10/22
VisualStudio 2012 Update3 (2012.3, VC11)
The following two packages are compiled with VisualStudio 11 Update3 (v110 platform toolset) and thus the binaries are not compatible with Windows XP (but the libraries (.dll/.lib) might work with windows XP!). We recommend to use it with Windows Vista or above and please ensure you have the correct Visual Studio version installed. You can use the ENV variable OSG_3RDPARTY_DIR to auto configure CMake. Package details, content list and sources are available here
Small package for 32 & 64 bit https://download.osgvisual.org/3rdParty_VS2012.3_v110_x86_x64_V8b_small.7z - Last Update: V8 on 2013/07/22
Full package for 32 & 64 bit https://download.osgvisual.org/3rdParty_VS2012.3_v110_x86_x64_V8b_full.7z - Last Update: V8 on 2013/07/22
VisualStudio 10 (2010)
32 & (some) 64 bit 3rdParty_VC10_x86_x64.zip
VisualStudio 9 (2008) SP1
32 & 64 bit http://download.osgvisual.org/3rdParty_VC9sp1_x86_x64_V7.7z - Last Update: V7 on 2011/06/29 - Details, content list and sources are available here - Use the ENV variable OSG_3RDPARTY_DIR to auto configure CMake.
Linux pre packaged dependencies
Under Debian GNU/Linux you can also make use of the pre-packaged binaries and run apt-get build-dep openscenegraph to download and install the necessary dependencies.
 

A quick dependencies guide follows.
Plugins :
The plugins are all optional, many of which have no further requirements beyond the core libraries so will compile straight out of the box. Other plugins require 3rd party libraries to be installed to allow them to be compiled. If you don't need to compile and plugin that is at present being compiled by default simply comment it out of the Make/makedirdefs file under Unix or unselect that particular plugin in VisualStudio's batch build. Follows is a list of dependencies and where to download them for each set of platforms.
file format	Plugin source code in the OSG distribution	Windows	OSX	Unix
tiff images	src/osgPlugins/tiff	tiff from the gnuwin32 repository	Fink or (see note on Quicktime)	libtiff
jpeg images	src/osgPlugins/jpeg	jpeg from the gnuwin32 repository	Fink or (see note on Quicktime)	libjpeg
gif images	src/osgPlugins/gif	libungif from the gnuwin32 repository	Fink or (see note on Quicktime)	libungif
png images	src/osgPlugins/png	libpng from the gnuwin32 repository	Fink or (see note on Quicktime)	libpng & libz
true type fonts	src/osgPlugins/freetype	freetype from the gnuwin32 repository	Fink or freetype	freetype
performer .pfb's	src/osgPlugins/pfb	Performer (now discontinued)	Performer is not available	Performer - for Linux and IRIX (now discontinued)
Notes, under OSX you can use Quicktime along with the src/osgPlugins/quicktime plugin to load tiff, jpef, gif and png images formats so you don't need to compile the related plugins.
