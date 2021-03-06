[![version](https://img.shields.io/badge/version-0.1.5-brightgreen.svg)](https://github.com/alexzaitsev/apk-dependency-graph/releases/tag/0.1.5) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-apk--dependency--graph-blue.svg?style=flat)](http://android-arsenal.com/details/1/4411) [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Android%20dependency%20visualizer&url=https://github.com/alexzaitsev/apk-dependency-graph&hashtags=android,dependency,coupling,graph,visualize,baksmali,developer)


Android dependency visualizer. It's a tool that helps to visualize current state of your project. It's really easy to see how tight your classes are coupled.

## Theory

Class coupling is one of the significant code metrics which shows how easy is to change your code. Actually the architecture of microservices is based on the idea that the modules should be low-coupled so you are able to easily replace one module with another one with the same interface. This tool helps to view whole picture of your project. Check yourself!

## Project structure

This project consists of the several parts:
* lib (baksmali)
* src, build (apk-dependency-graph)
* gui (d3)
* run scripts  
###### To get more information please check our [wiki page](https://github.com/alexzaitsev/apk-dependency-graph/wiki).

## Compile 

To compile `build/jar/apk-dependency-graph.jar` you need:
* **ant 1.9.9** or newer.
* at least **Java 5**  
From terminal just move to the parent folder of the project and run `ant` command. Classes will be generated to `build/classes` folder and jar file will appear onto `build/jar` folder.

## Run

You need at least **Java 7** to run `apk-dependency-graph` `jar` file.

## Usage

### Fast way
I've prepared helpful scripts for you. All you need to do is to download and unpack [the latest release](https://github.com/alexzaitsev/apk-dependency-graph/releases) and type the next command in your command line:  

*For Windows*:
```
run.bat full\path\to\the\apk\app-release.apk com.example.test true
```
or  
```
run.bat full\path\to\the\apk\app-release.apk nofilter false
```
where `run.bat` is a path to script in your local repository, `full\path\to\the\apk\app-release.apk` is a full path to the apk file you want to analize, `com.example.test` is a filter. **We recommend to use your package name as a filter so you will avoid unnecessary dependencies in your graph. If you don't want to filter just pass `nofilter`.** The last argument defines whether you want to skip inner classes on your graph (_true_ to skip, _false_ otherwise).  

*For Unix*:
```
./run.sh full/path/to/the/apk/app-release.apk com.example.test true
```
or  
```
./run.sh full/path/to/the/apk/app-release.apk nofilter false
```  
Wait until the command finishes:
```
Baksmaling classes.dex...
Success! Now open index.html in your browser.
```
It will decompile your apk and create `apk-file-name` folder in the same folder where the script is. After this it will analyze the smali code and generate `gui/analyzed.js` file which contains all dependencies.   
**Now open `gui/index.html` in your browser and enjoy!**

## Examples

Here is the sample of good architecture with low class coupling:  
![Good sample](image-good-example.jpg)

And this one looks like a spaghetti:  
![Good sample](image-bad-example.jpg)

Does your project look like the first or the second picture? :)

## Demo

Watch [demo video](https://www.youtube.com/watch?v=rw501tvT4ko).

## Hashtag

Share your awesome architecture using `#apkdependencyvizualizer` hashtag!

---

## Credits

There is the same tool for iOS: https://github.com/PaulTaykalo/objc-dependency-visualizer   
I have used `gui/index.html` of that project. Thanks Paul for the great tool.

## Contributors

I want to say thank you to all the people who made even tiny pull request. This project is intended to improve current state of Android architecture all over the world so each detail is important. Below you can find a list of people who have found some time to improve this tool:

* [WarrenFaith](https://github.com/WarrenFaith)
* [victorrattis](https://github.com/victorrattis)

##### Btw we still need contributors!  
Yes, we really need you man! We always have something to do and have special label for such issues. If you want to add or edit something on this tool - [welcome](https://github.com/alexzaitsev/apk-dependency-graph/issues?q=is%3Aissue+is%3Aopen+label%3A%22contributors+wanted%22)!  

## Dependency Injection Graph

If you're looking for an Android Studio plugin that allows to display graph of dependency injections - please check out [this repository](https://github.com/kaygisiz/Dependency-Injection-Graph). It's based on current project and available in [Jetbrains repository](https://plugins.jetbrains.com/plugin/10107-dependency-injection-graph).

## Share a link to our repository
[![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Android%20dependency%20visualizer&url=https://github.com/alexzaitsev/apk-dependency-graph&hashtags=android,dependency,coupling,graph,visualize,baksmali,developer)
