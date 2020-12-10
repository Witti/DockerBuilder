# PHP Docker Command Builder

### Installation

`composer require matusboa/docker-builder`

### Requirements

- PHP 7.4

### Usage

```php
use MatusBoa\DockerBuilder\Builder;
use MatusBoa\DockerBuilder\Volume;
use MatusBoa\DockerBuilder\Port;

// docker run -d -p 80:80 -v /some/directory:/some/directory testImage
$command = Builder::new("testImage")
    ->mapPort(new Port(80, 80))
    ->mountVolume(new Volume("/some/directory", "/some/directory"))
    ->detached()
    ->build();
```

### Available methods

#### withName

Adds `--name` to the command.

##### mapPort

Adds `-p` to the command.

##### mountVolume

Adds `-v` to the command.

##### limitRam

Adds `--memory` to the command.

##### restartPolicy

Adds `--restart` to the command.

##### detached

Adds `-d` to the command.


