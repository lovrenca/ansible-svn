# SVN ansible role
This ansible role sets up SVN in conjecture with apache using dav_svn apache mod.

## Optional variables
* svn_aditional_packages - optional apt packages to install
* svn_usvn - Install usvn
* svn_usvn_data_dir - where to save usvn data
* svn_repositories - list of svn repositories
  * name: name of the repository (no whitespaces)
  * url: Url to use for the repository
  * storage: Location for the SVN repository
  * ssl_cert: path to ssl certificate for apache to use - setting this triggers use of ssl
  * ssl_key: path to ssl key for apache to use
* svn_usvn_repositories: List of usvn repositories
  * name: name of the repository ( no whitespaces)
  * port: Port to listen on (443 - probably)
  * url: domain
  * storage path for svn data
  * install_path: Where to instal usvn
  * auth_name: User friendly greeting when asked for a password
  * ssl_key: Path to ssl key to use
  * ssl_cert: Path to ssl cert to use - setting this triggers use of ssl

## PSVN
Installs fresh install of USVN.
Svn repositories will be under /svn path.

### Post run
After installing usvn with Ansible, navigate to <URL>/install.php to complete
the installation. Again - it is presumed that this is a fresh install.
Use the same value as svn_usvn_data_dir variable for svn path and for dirname of
other variable(auth, db file...).
