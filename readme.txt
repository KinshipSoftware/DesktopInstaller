This desktop installer project has been created from the desktop installer scripts that were created
for Arbil then made generic for use in KinOath and other projects.

How to configure the installer script
=====================================

To use this installer in your project, execute the following steps:

- In your project directory, type
	`svn propset svn:externals "^/DesktopInstaller/trunk installer" .`
  If your directory already has svn externals, use `svn propedit svn:externals .` so they don't get
  overwritten!
- Perform an svn update in that directory. The 'installer' directory will be
  added to the project.
- Go to the 'installer/ant-deb-jar' directory and download the following
  file: <http://ant-deb-task.googlecode.com/files/ant-deb-0.0.1.jar>.
- Copy the file 'installer/application.properties.example' to your project
  directory as 'application.properties'. Open it in an editor, set all the
  values correctly, and put it under version control.
- If you want to use the script to deploy to the server, download the jar
  package for JSch from <http://www.jcraft.com/jsch/> and put it in your ant
  lib path (e.g. ~/.ant/lib).

The installer expects a file 'version.properties' to be present in the target class directory after
compilation, with the following properties set:

-application.title
-application.iconName
-application.majorVersion
-application.minorVersion
-application.branch
-application.revision
-application.lastCommitDate
-application.compileDate
-application.currentVersionFile

To accomplish this, create a file of the same name in your src/main/resources directory. This file
can be filtered through maven in the pre-compile phases so that version info, SVN info etcetera
get inserted dynamically just before compilation.

How to use installer the script
===============================

To use the installer script run any of the ant targets, e.g.:
- maven-jar (will just create the jar in the target directory)
- scp_to_lux_09 (will create the installers and deploy them on lux09)

You will need Wine <http://www.winehq.org/> to build the windows installer.
