# MSVC Win32 Application

## Table of Contents

- [Introduction](#introduction)
- [Windows Target Version](#windows-target-version)
- [Distributing Your Application](#distributing-your-application)
- [Terms of Use](#terms-of-use)
- [Problems?](#problems)
- [Changelog](#changelog)

## Introduction

This application is an example Windows GUI application, intended to be used as a starting point for writing well
designed Win32 applications. It is a straight port of the
[MinGW Win32 Application](https://github.com/TransmissionZero/MinGW-Win32-Application), and has the following features:

- Resizable main window, with an empty client area.
- About dialog, with some basic text, an icon, and an "ok" button.
- Windows "visual styles" support, so that controls such as buttons are consistent with other Windows applications
  running with visual styles enabled.
- Version information resource, so that the version information and copyright information can be viewed using Windows
  Explorer.
- Main menu allowing exiting of the application, and the showing of the about dialog.
- Keyboard accelerator "Alt + A" to show the about dialog.
- System menu item allowing the about dialog to be shown.
- Unicode support.
- Target either 32 bit or 64 bit versions of Windows, without any source code changes.


To build the application, open the solution file in Visual Studio, right click the solution in the Solution Explorer and
select "Retarget solution". Choose which version of the Windows SDK you'd like to use to build the solution. Next,
select the configuration and platform from the drop-down menu, and use "Build Solution" from the "Build" menu.

The solution was created in Visual Studio 2017, but it should open in any version of Visual Studio from 2010 SP1
onwards.

## Windows Target Version

The project targets Windows Vista. If you attempt to call Windows API functions in your source code which were
introduced after Windows Vista, you will get a compilation error. If you'd like to use newer API functions (at the
expense of the application not running on older versions of Windows), you will need to change the "_WIN32_WINNT"
preprocessor definition in "targetver.h" to match the version of Windows you are targeting. For example, to target
Windows 7, change it to "0x0601".

You can also target Windows XP using the above method with the value "0x0501". However, you will also need to go into
your project properties, and set the "Platform Toolset" under "Configuration Properties" to a toolset which supports
Windows XP.

You can find a complete list of target version numbers in the "SDKDDKVer.h" Windows SDK header file.

## Distributing Your Application

The application will depend on the Microsoft Visual C++ Runtime. This will either be in the form of a Visual C++ Runtime
redistributable MSI (or merge module which you can use in your own installer), or DLL(s) which you must redistribute
with the application. Check the product documentation for your version of Visual Studio to see what your options are,
and be careful to ensure that you are allowed to redistribute the DLL(s) if you choose this option.

## Terms of Use

Refer to "License.txt" for terms of use.

## Problems?

If you have any problems or questions, please ensure you have read this readme. If you are still having trouble, you can
[get in contact](http://www.transmissionzero.co.uk/contact/).

## Changelog
1. 2017-05-07: Version 1.0
  - Initial release.

Transmission Zero
2017-05-07
