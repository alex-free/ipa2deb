# [alex-free.github.io](https://alex-free.github.io)

## IPA2DEB

By Alex Free

The [.ipa](https://www.theiphonewiki.com/wiki/IPA_File_Format) file format is the official way iOS applications are distributed by Apple. For older devices that can no longer use the AppStore or other means, these files can be installed manually after they are 'decrypted' (untied from the specific AppleID used to purchase/download them) using various methods.

I think there is a better way to manage applications originally distributed in the `.ipa` file format. That is, to convert decrypted `.ipa` files to the format that jailbreak-only software/tweaks are distributed in traditionally, known as `.deb`.

## External Links

*   [Homepage](https://alex-free.github.io/ipa2deb) 
*   [GitHub](https://github.com/alex-free/ipa2deb)

## Table Of Contents

*   [Downloads](#downloads)
*   [Usage](#usage)
*   [License](#license)

## Downloads

### v1.0 (2/27/2023)

[IPA2DEB v1.0](https://github.com/alex-free/ipa2deb/releases/download/v1.0/ipa2deb-1.0.zip)


## Usage

IPA2DEB requires 4 arguments:

1) The filepath of the `.ipa` file you want to convert, **or** a directory of `.ipa` files (that IPA2DEB will bulk convert recursively).

2) The filepath of the the output directory, where your converted `.deb` files will be written to as well as any error `.txt` log files.

3) Your contact info: first name, last name, email (all in quotes). Something like `"Your Name <Your_Name@youremail.com>"`.  You don't have to really put an email here though if you'd rather not.

4) Your website URL (used for `.deb` related info).

There are 3 possible log files that may be generated during conversion by IPA2DEB:

*   `ipa2deb-extraction-failure-log.txt` will be generated if a `.ipa` file can not be extracted to be further processed.
*   `ipa2deb-conversion-failure-log.txt` will be generated if `dpkg-deb` fails to build a `.deb` file out of the original `.ipa` file due to missing required information.
*   `ipa2deb-duplicate-packages-log.txt` will be generated if any files are created more then once. The resulting duplicate deb files will be placed in a `duplicates` directory, which will be removed on the next run of IPA2DEB if the output directory (2nd argument) remains the same.

These log files will be mentioned at the end of a conversion if they are generated. All files mentioned above are placed in the same output directory as the converted `.deb` files, specified by the 2nd argument given to IPA2DEB.

There is an additional script available in each IPA2DEB release, `genrepo`. This script requires 1 argument, a directory of `.deb` file(s). It will generate a `Packages.gz` and turn the directory into a valid Cydia repo that can be uploaded on a server to use.

## License

IPA2DEB is released into the public domain, see the file `unlicense.txt` for more info.