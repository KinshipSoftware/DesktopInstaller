This desktop installer project has been created from the desktop installer scripts that were created for Arbil then made generic for use in KinOath and other projects.

To use this installer in your project, execute the following steps:

- In your project directory, type `svn propset svn:externals "^/DesktopInstaller/trunk installer" .`
  (If your directory already has svn externals, use `svn propedit svn:externals .` so they don't get
  overwritten.
- Perform an svn update in that directory. The 'installer' directory will be
  added to the project.
- Go to the 'installer/ant-deb-jar' directory and download the following
  file: <http://ant-deb-task.googlecode.com/files/ant-deb-0.0.1.jar>.
- Copy the file 'installer/application.properties.example' to your project
  directory as 'application.properties'. Open it in an editor, set all the
  values correctly, and put it under version control.

- To use the installer script run any of the ant targets, e.g.:
* maven-jar (will just create the jar in the target directory)
* scp_to_lux_09 (will create the installers and deploy them on lux09)

You will need Wine <http://www.winehq.org/> to build the windows installer.

