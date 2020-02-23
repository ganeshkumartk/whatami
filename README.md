<h1 align="center">
  <br>
  <a href="https://www.npmjs.com/package/whatami"><img src="https://tapkins.com/wp-content/uploads/2017/11/tapkins_GWAI_intro-2-uai-1080x720.png" alt="whatami" width="200"></a>
  <br>
   😎 'whatami' <a href="https://badge.fury.io/js/whatami"><img src="https://badge.fury.io/js/whatami@2x.png" alt="npm version" height="18"></a>
  <br>
</h1>
<h4 align="center">Find Whatsoever in image with the convenience of Machine learning at CLI!</h4>

## Basic usage

At it's core, `whatami` is a tool that allows you to identify the objects contained in an image file. 

It does this by leveraging the power of the [MAX Image Segmenter model](https://developer.ibm.com/exchanges/models/all/max-image-segmenter/), one of the many free-to-use, open-source deep learning models available on [IBM's Model Asset eXchange](https://developer.ibm.com/code/exchanges/models/). The model has been converted to a [TensorFlow.js](https://tensorflow.org/js) implementation and the app runs entirely in Node.js.

In addition to displaying an image's contents, `whatami` has extended this functionality by offering several commands that allow you to search over directories with multiple images for certain objects, save individual objects as new image files, show in-terminal previews of objects, and more.

## Installation Instructions

Install using `npm` to automatically add the `whatami` command to your PATH.
~~~bash
$ npm i -g whatami
~~~

That's it! 

Now you can begin using `whatami` like your very own command-line crystal ball 🔮 to identify what objects are contained in an image.

### Prerequisites

- Node.js v10.x or higher. Install from [here](https://nodejs.org/en/download/).

## Basic Commands

Keep reading for quick-and-easy install instructions, some information on the basic commands that are available and some GIFs to help you get started.
<p align="center">
  <img src="/assets/whatami.svg">
</p>

Use the basic command `whatami </path/image_name>` to **identify** what objects are contained in an image. If you have multiple images you'd like to inspect, you can also provide the name of a directory containing image files.

To **scan a directory** of images for a certain object, use the `--contains` command. When used in combination with the `--verbose` option, the results for all images in a directory will be displayed. 

If you'd like to see an in-terminal **preview** of any of these objects, use the `--show` flag, followed by the name of the object you'd like to see. You can specify the 'colormap' to see all the objects highlighted within the original image.

<p align="center">
  <img src="/assets/whatami_car.svg" height="300" width="500">
</p>

To **save** any of the objects as individual image files, use the `--save` flag, followed by the name of the object you'd like to save, or use 'all' to save all objects.

To **remove** an object or background from an image, use the `--remove` flag, followed by the name of the object you'd like to remove or the shorthand aliases 'bg' or 'BG' to remove the background.

> For more detailed usage information, see the in-app **help page** which can be accessed by executing `whatami -h`

## Synopsis

  ~~~bash
  $ whatami <file> [--command]      
  $ whatami <directory> [--command] 
  $ whatami [--help | -h]  
  ~~~

## Command List

| Commands  |  Usage |
|:-:|:-:|
| `save <object>`  | Save the specfied object to it's own file. Also works with 'all'. |
| `remove <object>`| Save a copy of the image with the specfied object (or background) removed. Supports aliases 'bg' and 'BG'.|
|  `show <object>` |  Show the specified object (or the entire image if blank) in the terminal. |
|  `contains object [--verbose]` | Returns list of images containing the specified object. (Use --verbose option to see all results).  |

## Examples

  1. Examine objects contained in an image.                             
  ~~~bash
  $ whatami path/to/IMAGE.PNG
  ~~~
  2. Show the 'dining table' from sample.jpg.                           
  ~~~bash
  $ whatami sample.jpg --show 'dining table'
  ~~~
  3. Scan the 'pets' directory for images containing a dog.             
  ~~~bash
  $ whatami pets/ --contains Dog          
  ~~~
  4. Remove the background from all images in the current directory.    
  ~~~bash
  $ whatami . --remove BG
  ~~~

## Detectable Objects

|  Objects | Objects  |
|:-:|:-:|
|Airplane|   Dining Table |
| Bicycle  |  Dog |
|  Bird | Horse  |
|  Boat |  Motorbike |
| Bottle  | Person  |
|Bus   | Potted Plant  |
| Car  |Sheep|
| Cat  | Sofa  |
|Chair|Train|
|Cow|TV|


## Licenses

| Component | License | Link  |
| ------------- | --------  | -------- |
| This repository | [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) | [LICENSE](LICENSE) |
| Model Code (3rd party) | [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) | [TensorFlow Models Repository](https://github.com/tensorflow/models/blob/master/LICENSE) |
| Model Weights | [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) | [TensorFlow Models Repository](https://github.com/tensorflow/models/blob/master/LICENSE) |
