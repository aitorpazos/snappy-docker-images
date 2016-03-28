# ubuntu-juju-builder

You can use this image to build the following juju binaries for your Linux architecture of choice:

* juju
* jujud
* juju-metadata

## Parameters

You can customise the building process using the following environment variables:

* USER_UID
Adjust this value to the uid of the user that owns the volume where the generated binary will be saved (Default 1000).

* JUJU_ARCH
Set the linux architecture for which you want the juju binary to be generated. Valid options are: 386, amd64, armhf and arm64 (Default amd64).

* JUJU_ARCH_VER (Only relevant when JUJU_ARCH = armhf)
Use it to select the ARM version to be used (Default 7). Check <https://github.com/golang/go/wiki/GoArm> for all valid values.

## Run

To run this image, you should adjust the USER_UID environment variable and set the volume where the generated binary should be saved.

Example:
```
docker run -e USER_UID=1000 -v <volume_path>:/work aitorpazos/ubuntu-juju-builder
```

