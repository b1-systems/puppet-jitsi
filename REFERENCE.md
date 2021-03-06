# Reference
<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

**Classes**

* [`jitsi`](#jitsi): Configures a Jitsi Meet instance.
* [`jitsi::repo`](#jitsirepo): Configure binary package repository for Jitsi Meet

## Classes

### jitsi

Configures a Jitsi Meet instance.

#### Parameters

The following parameters are available in the `jitsi` class.

##### `authentication`

Data type: `Enum[
    'ldap',
    'local',
    'none'
  ]`

What kind of authentication to use.

##### `authentication_options`

Data type: `Hash`

List of parameters to use for the authentication provider; provider-dependent.

##### `hostname`

Data type: `Stdlib::Fqdn`

Host name to use for the installation.

##### `manage_repo`

Data type: `Boolean`

If the repository should be managed by this module. (default: true)

##### `manage_service`

Data type: `Struct[{
    'webserver' => Boolean,
  }]`

Whether to manage certain services.

Options:

* **:webserver** `Boolean`: Manage the webserver service. Default: +true+

##### `packages`

Data type: `Variant[
    Enum['all'],
    Array[
      Enum[
        'jitsi-meet-web',
        'jitsi-videobridge',
        'jicofo',
        'jigasi'
      ]
    ]
  ]`

Either 'all' or a list of jitsi packages to install. (default: 'all')
Valid choices: *jitsi-meet-web*, +jitsi-videobridge+, +jicofo+, +jigasi+

##### `release`

Data type: `Jitsi::Release`

Which release (stable, testing, nightly) to use (default: stable)

##### `secrets`

Data type: `Struct[{
    Optional[focus]      => String[1],
    Optional[focus-user] => String[1],
    Optional[video]      => String[1],
  }]`

Secrets to define for the components. Will default to a string based on the host name.
Possible keys: +component+, +focus+, +focus_user+ +video+

##### `ssl`

Data type: `Struct[{
    certificate => Stdlib::Unixpath,
    key         => Stdlib::Unixpath,
  }]`

Location to SSL +certificate+ and +key+. No default.

##### `webserver`

Data type: `Enum[
    'apache',
    'nginx',
    'none'
  ]`

Which web server to use for serving the content.
Currently supported: +nginx+.

##### `www_root`

Data type: `Stdlib::Unixpath`

Installation location of the jitsi meet files.

### jitsi::repo

Configures the official binary package repository for Jitsi Meet

#### Parameters

The following parameters are available in the `jitsi::repo` class.

##### `fingerprint`

Data type: `Stdlib::Base64`

Fingerprint of the repository key

##### `release`

Data type: `Jitsi::Release`

Which release to use. (+stable+, +testing+, +nightly+)

