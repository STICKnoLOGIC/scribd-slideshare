# Scribd-SlideShare ![nodedotjs](https://img.shields.io/badge/node.js-v21.6-339933.svg?style=flat&logo=nodedotjs&logoColor=white) ![npm](https://img.shields.io/badge/npm-10.2-dc2c35.svg?style=flat&logo=npm&logoColor=white)  

## About ##
Scribd-SlideShare helps downloading:
- documents on [scribd.com](https://www.scribd.com/) and [slideshare.net](https://www.slideshare.net/) without membership / sign-in  
- podcast audios on [everand.com](https://www.everand.com/podcasts)  

## Prerequisites ##
To use Scribd-SlideShare, you need to install [Node.js](https://nodejs.org/en/) and [Git](https://git-scm.com/downloads). It is recommended that you use the latest LTS version available.  

> Please install Node.js using pre-built installers for your platform. You may encounter incompatibility issues with different development tools otherwise.  

To check that Node.js was installed correctly, type the following commands in your terminal client:  
```console
node -v
npm -v
```
The commands should print the versions of Node.js and npm accordingly.  

## Setup ##
1. Download repository  
```console
git clone https://github.com/CJKennedy00/scribd-slideshare
```
2. Install dependencies
```console
cd ./scribd-slideshare
npm install
```
3. Run this to make sure some fix errors fixed:
```console
npm audit fix --force
```

## Configuration ##
Configuration can be altered in `config.ini`.  
```ini
[SCRIBD]
rendertime=100

[DIRECTORY]
output=output
```
`rendertime` is the waiting time in millisecond for single page rendering on [scribd.com](https://www.scribd.com/), it is only applicable for `default` mode.  
`output` is the ouput directory for generated .pdf files.

## Usage (CLI) ##
```console
Usage: npm start [options] url
Options:  
  /i        image-based: generated by image snapshots taken for pages on scribd.com
```

#### Example 1: Download 《The Minds of Billy Milligan》 on scribd.com ####
```console
npm start "https://www.scribd.com/doc/249398282/The-Minds-of-Billy-Milligan-Daniel-Keyes"
```

#### Example 2: Download 《The Minds of Billy Milligan》 using `image-based` method on scribd.com ####
```console
npm start /i "https://www.scribd.com/doc/249398282/The-Minds-of-Billy-Milligan-Daniel-Keyes"
```

#### Example 3: Download 《Everything You Need To Know About ChatGPT》 on slideshare.net ####
```console
npm start "https://www.slideshare.net/slideshow/everything-you-need-to-know-about-chatgpt-8ba3/266783915"
```

#### Example 4: Download all 《TED Talks Daily》 episodes on everand.com ####
```console
npm start "https://www.everand.com/podcast-show/414106971/TED-Talks-Daily"
```

#### Example 5: Download 《Sunday Pick: How to care for the people who take care of us (w/ Ai-jen Poo)》 on everand.com ####
```console
npm start "https://www.everand.com/listen/podcast/731670963"
```

## Support URL Format ##
- https://www.scribd.com/doc/**
- https://www.scribd.com/embeds/**
- https://www.slideshare.net/**
- https://www.slideshare.net/slideshow/**
- https://www.everand.com/podcast-show/**
- https://www.everand.com/podcast/**
- https://www.everand.com/listen/podcast/**

## Development Plan ##

- Scribd obfuscates the .pdf files, the texts copied from the documents might become strange garbled message. De-obfuscating is one of the future plan.

## License ##
This project is licensed under the [MIT License](LICENSE.md)
