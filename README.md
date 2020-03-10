<h1 align="center">
  Amazon Kinesis Video Streams C Producer
  <br>
</h1>


<h4 align="center"> Amazon Kinesis Video Streams | Secure Video Ingestion for Analysis &amp; Storage </h4>

<p align="center">
  <a href="https://travis-ci.org/awslabs/amazon-kinesis-video-streams-producer-c"> <img src="https://travis-ci.org/awslabs/amazon-kinesis-video-streams-producer-c.svg?branch=master" alt="Build Status"> </a>
  <a href="https://codecov.io/gh/awslabs/amazon-kinesis-video-streams-producer-c"> <img src="https://codecov.io/gh/awslabs/amazon-kinesis-video-streams-producer-c/branch/master/graph/badge.svg" alt="Coverage Status"> </a>
</p>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#build">Build</a> •
  <a href="#run">Run</a> •
  <a href="#documentation">Documentation</a> •
  <a href="#related">Related</a> •
  <a href="#license">License</a>
</p>

## Key Features
Amazon Kinesis Video Streams Producer SDK for C/C++ makes it easy to build an on-device application that securely connects to a video stream, and reliably publishes video and other media data to Kinesis Video Streams. It takes care of all the underlying tasks required to package the frames and fragments generated by the device's media pipeline. The SDK also hand
les stream creation, token rotation for secure and uninterrupted streaming, processing acknowledgements returned by Kinesis Video Streams, and other tasks.

## Build
### Download
To download run the following command:

`git clone --recursive https://github.com/awslabs/amazon-kinesis-video-streams-producer-c.git`

Note: If you miss running git clone with --recursive, run `git submodule update --init` in the amazon-kinesis-video-streams-producer-c/open-source directory
You will also need to install `pkg-config`, `automake` and `CMake` and a build enviroment

### Configure
Create a build directory in the newly checked out repository, and execute CMake from it.

`mkdir -p amazon-kinesis-video-streams-producer-c/build; cd amazon-kinesis-video-streams-producer-c/build; cmake .. `

By default we download all the libraries from GitHub and build them locally, so should require nothing to be installed ahead of time.
If you do wish to link to existing libraries you can use the following flags to customize your build.

#### Cross-Compilation

If you wish to cross-compile `CC` and `CXX` are respected when building the library and all its dependencies. See our [.travis.yml](.travis.yml) for an example of this. Every commit is cross compiled to ensure that it continues to work.


#### CMake Arguments
You can pass the following options to `cmake ..`.

* `-DBUILD_DEPENDENCIES` -- Whether or not to build depending libraries from source
* `-DBUILD_TEST=TRUE` -- Build unit/integration tests, may be useful for confirm support for your device. `./tst/webrtc_client_test`
* `-DCODE_COVERAGE` --  Enable coverage reporting
* `-DCOMPILER_WARNINGS` -- Enable all compiler warnings
* `-DADDRESS_SANITIZER` -- Build with AddressSanitizer
* `-DMEMORY_SANITIZER` --  Build with MemorySanitizer
* `-DTHREAD_SANITIZER` -- Build with ThreadSanitizer
* `-DUNDEFINED_BEHAVIOR_SANITIZER` Build with UndefinedBehaviorSanitizer
* `-DALIGNED_MEMORY_MODEL` Build for aligned memory model only devices. Default is OFF.

### Build
To build the library run make in the build directory you executed CMake.

`make`

## Documentation

## Related

## License

This library is licensed under the Apache 2.0 License.
