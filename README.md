# Arborealis Vision

## Entoptic 

OSC Client that spits data based on camera input in the form of an OSC string packet for every frame that look like:

```
[/A/C1 OSC-string:'0.934847,0.967667,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0.918743,0,0,0,0,0.933927,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0.983912,0,0,0.981289,0,0,0,0,0,0,0,0.928788,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0.954362,0.958915,0,0,0,0,0.906563,0,0,0,0.980445,0,0,0.962922,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0.931076,0,0,0.995334,0,0,0,0,0,0,0,0.982881,0,0,0,0,0,0,0,0,0.919610,0,0,0,0,0,0.956571,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0.917023,0,0.931294,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0']
```
The cell values start at the left corner of the instrument/camera grid and read left to right, top to bottom. The framerate is currently set to 30 frames per second, but will be editable in future versions.


### Requirements
Only tested on mac. Your milage may vary translating these steps to other environments.

* homebrew
  * ```ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```
* git
 * ```brew install git```
* cmake and pkg-config
 * ```brew install cmake pkg-config```
* boost
 * ```brew install boost```
* opencv
 * ```brew install eigen ffmpeg openexr tbb``` 
 * ```brew tap homebrew/science```
 * ```brew install opencv```


### Installation
* ```git clone https://github.com/arborealis/vision.git```
* ```cd vision/entoptic```
* ```mkdir build```
* ```cd build```
* ```cmake ..``` 
* ```make```


### Usage
* ```./bin/entoptic [optional path to video file for input] [optional ip address of server] [optional port]```
 * the ip address deafults to 127.0.0.1, and port to 7000, e.g. ```./bin/entoptic 127.0.0.1 7000``` or just ```./bin/entoptic``` to get the defaults.
* if you want to see the raw data being spit out, open the same directory in a different terminal window and run ```./bin/OscDump```

