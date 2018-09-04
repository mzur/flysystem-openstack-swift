# Flysystem Adapter for OpenStack Swift

[![Build Status](https://img.shields.io/travis/mzur/flysystem-openstack-swift/master.svg?style=flat-square)](https://travis-ci.org/mzur/flysystem-openstack-swift)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Packagist Version](https://img.shields.io/packagist/v/mzur/flysystem-openstack-swift.svg?style=flat-square)](https://packagist.org/packages/mzur/flysystem-openstack-swift)

Flysystem adapter for OpenStack Swift.

This is a fork of [nimbusoftltd/flysystem-openstack-swift](https://github.com/nimbusoftltd/flysystem-openstack-swift) as the original maintainer has been inactive.

## Installation

```bash
composer require mzur/flysystem-openstack-swift
```
## Usage

```php
$openstack = new OpenStack\OpenStack([
    'authUrl' => '{authUrl}',
    'region'  => '{region}',
    'user'    => [
        'id'       => '{userId}',
        'password' => '{password}'
    ],
    'scope'   => ['project' => ['id' => '{projectId}']]
]);

$container = $openstack->objectStoreV1()
    ->getContainer('{containerName}');

$adapter = new Nimbusoft\Flysystem\OpenStack\SwiftAdapter($container);

$flysystem = new League\Flysystem\Filesystem($adapter);
```
