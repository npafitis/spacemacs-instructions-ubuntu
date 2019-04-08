Instructions for Installing Emacs with spacemacs clean on Ubuntu(16.04) Step by Step
===

## Step 1. Installing emacs
Some of spacemacs dependencies (like helm-projectile) now require an emacs version >25.x

This could be a problem especially since Ubuntu 16.04 comes with version 24.4.

 - Easiest way to install new version of emacs i found to be downloading the release you'd like from any GNU Mirror(preferrably >25.3 ) found here:
      
    https://www.gnu.org/software/emacs/download.html#gnu-linux

    Just click the __nearby GNU mirror__ link and download the tar file with the version you'd like. In my case __emacs-25.3.tar.gz__
 - Then open a terminal (ctrl + alt + t) and run:
    ``` bash
    tar xvf emacs-25.3.tar.gz /your/path/emacs-25.3
    cd /your/path/emacs-25.3
    chmod +x configure
    ./configure
    ```
    Now, after running the configure shell script successfully without errors, a makefile will be generated.
    
- IN CASE of errors running ./configure

    There's a chance that errors will pop out saying that packages like libXpm, libgif, libjpeg, libtiff cannot be found.
    In that case run in your terminal:
    ``` bash
    sudo apt-get install libxpm-dev
    sudo apt-get install libjpeg-dev
    sudo apt-get install libtiff5-dev
    sudo apt-get install libgif7-dev
    sudo apt install libpng16-dev
    sudo apt install libxaw7-dev
    ```
    for the packages that you are missing. <br/>
    In short, Packages with the "-dev" suffix are headers needed for other software to use these libraries.
    
    Also make sure you have GTKTerm installed.
    ```bash
    sudo apt-get install gtkterm
    ```
- After you have successfully ran ./configure run:
    ```bash
    make
    make install
    ```
    Now you should have installed emacs properly.

## Step 2. Installing spacemacs.
Steps for Installing spacemacs are written more concisely here: https://github.com/syl20bnr/spacemacs.

- Make a backup of your existing emacs configuration (if you have any):
    ```bash
    cd ~
    mv .emacs.d .emacs.d.bak
    mv .emacs .emacs.bak
    ```
- Clone the repository:
    ```bash
    git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
    ```

Now spacemacs is ready to be used although you most likely will need [Source Code Pro](https://github.com/adobe-fonts/source-code-pro) Pro fonts.

## Step 3. Installing Space Code Pro.
Easiest way to install Space Code Pro system wide is through [npm](https://www.npmjs.com/), if you don't have it already you can get it [Here](https://www.npmjs.com/get-npm).

- After installing npm run in your terminal the following:
    ```bash
     npm install git://github.com/adobe-fonts/source-code-pro.git#release --global
    ```

Now hopefully you should be ready to use spacemacs to it's full potential.

Feel free to post any issues regarding these instructions.
