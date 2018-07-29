# Installation

## Computer

### Installation

> The following guide provides instructions and resources to help developers set up the development environment, build the IoTivity stack and build sample applications on Ubuntu for a Linux target. Developers should also read the IoTivity Programmer's Guide before starting development to better understand IoTivity architecture and use cases.

[https://www.iotivity.org/documentation/linux/getting-started ](https://www.iotivity.org/documentation/linux/getting-started)

### Device Set-up

> As IoTivity is a framework for device-to-device connectivity, we must set-up a device we are going to use for this. As said in the Pre-Work section, we use a Ubuntu 15.04 Linux machine. Follow the tutorial in the link below to set-up your Ubuntu Linux machine. [https://www.iotivity.org/documentation/linux/getting-started](https://www.iotivity.org/documentation/linux/getting-started) The set-up intends to configure a connection between your device and Gerrit Code Review. There are 2 methods to get the source code. [_Downloading most stable source from here._](https://www.iotivity.org/downloads) __Getting source directly from gerrit. Download the source code and untar in a working folder. Inside the source code folder, clone the following repository. We need to modify a line in a source file. `git clone https://github.com/01org/tinycbor.git extlibs/tinycbor/tinycbor` To finish the IoTivity setup, make sure an internet connection is stablish and follow the following steps specified in the getting started page. _Build the IoTivity project for Linux_ Run a sample \*Build the API reference documentation

#### Errors and Solutions

> In one of the IoTivity versions, there is one line of code that is wrong but fixed in the master branch in Github. In the file `BundleInfoInternal.cpp` under the path `iotivity/service/resource-container/src/`, in the `BundleInfoInternal::BundleInfoInternal()` constructor the variable m\_so\_bundle is assigned to nullptr, it should be false. Modify this and build \(run scons\) in the root of IoTivity folder. If we get the error below: Whenever we try to run scons tu build, it shows the following error: scons: building terminated because of errors. /usr/local/include/boost/utility/addressof.hpp:59:47: error: call of overloaded f\(boost::detail::addr\_impl\_ref std::nullptr\_t int\) is ambiguous.... Status: Figuring out how to fix this error Figured out. Access with root to the following file with your simple text editor of preference `/usr/local/include/boost/utility/addressof.hpp`, there is a line with the following code `static inline T * f( T * v, int )`, change int for long resulting in `static inline T * f( T * v, long )`. Build again, it should build successfully. Status so far: Build successful but it is not creating executables under `resource/examples`. Solution found. After the successful build, the folder that has the executables is not the same as the folder in the guide, the folder with the executables is `iotivity/out/linux/x86_64/release/resource/examples` or `iotivity-1.1.0/out/linux/x86_64/release/resource/examples` if we downloaded the code from the website, under our IoTivity working directory.

### Finish Set-Up

> Now, under the current directory of examples, run `./simpleserver`, is an example of a simple server using the observer pattern, when we run it, a resource will be created and it will be waiting for a subscriber. In another terminal and under the same working directory, run `./simpleclient`. Now, the subscriber called simpleclient will begin to find resources and to send and receive data, the data will be displayed in both terminals showing a sucessfull connection with IoTivity.

## Edison

> Iotivity 0.9 SDK [https://wiki.iotivity.org/running\_sample\_codes\_in\_iotivity\_0.9\_sdk\_on\_edison](https://wiki.iotivity.org/running_sample_codes_in_iotivity_0.9_sdk_on_edison) [https://videoportal.intel.com/media/Iotivity+Tutorial+-+Linux+%26+Edison/0\_3fmerocs](https://videoportal.intel.com/media/Iotivity+Tutorial+-+Linux+%26+Edison/0_3fmerocs) Status: reviewing IoTivity already installed in devkit 3.0, and differences with the one we can download.

