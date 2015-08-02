# [imageMe](./../../)

imageMe is a super simple image and video gallery server which can be run in both Python 2 and Python 3.

Think `python2 -m SimpleHTTPServer` or `python3 -m http.server` for pictures and HTML5 supported videos with multithreading support.

![](../gh-pages/images/screenshots/image_index.png)

## Super Duper Easy One Line Usage

To run the imageMe server on port 8000:

```bash
> curl https://cdn.rawgit.com/M157q/imageme/master/imageme.py | python
```

---

## Feature

+ Basic funtionality like `SimpleHTTPServer`
+ Multithreading
+ Images support
  + Use Pillow to generate thumbnails for better user experience. (Need to install Pillow)
+ HTML5 videos support (Depends on which browser you are using, you can check [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility) for futher details.)
+ Some additional CLI options

---

## Installation / Setup


### Step 1: Get the File

You can clone this repo:

```bash
> git clone https://github.com/M157q/imageme.git
```

Or just grab the file directly:

```bash
> wget https://cdn.rawgit.com/M157q/imageme/master/imageme.py
```

### Step 2: Setup

1. You can do nothing and just run the script by using `python imageme.py [options]` with the usage below.
2. You can add the dirpath of imageme.py into the `PATH` environment variable of your shell, then you can run imageMe simply with `imageme.py [options]`. (Don't forget to set it to executable by `chmod` command first.)
3. If you want the same like `python2 -m SimpleHTTPServer` or `python3 -m http.server`, you can create a soft link for imageme.py in the `site-packages` directory of your python lib or just copy it to there. After that, you can just use `python -m imageme [options]` to run the imageMe server. (The more convenient way with this is installing via pip, I will add a setup.py for this in the future.)

About the `[options]`, you can see the Manual / Usage section below.

---

## Manual / Usage

```
usage: imageme.py [-h] [-d DIR] [-i INDEX_FILE_NAME] [-c COLUMN] [-w WIDTH]
                  [-s]
                  [port]

positional arguments:
  port                  The port number for server to listen. (default: 8000)

optional arguments:
  -h, --help            show this help message and exit
  -d DIR, --dir DIR     The root directory for server to run. (default:
                        current directory)
  -i INDEX_FILE_NAME, --index-file-name INDEX_FILE_NAME
                        The html filename for every directory. (default:
                        imageme)
  -c COLUMN, --column COLUMN
                        Number of columns per row for table. (default: 3)
  -w WIDTH, --width WIDTH
                        The width in pixels for every thumbnail. (default:
                        800)
  -s, --separate-image-and-video
                        Separate the images and the videos in webpage
                        arrangement.
```

---

## Example

### How to run imageMe

Run `imageme.py` / `python imageme.py` / `python -m imagme` (Depends on which installation you used, here I will use `python -m imageme` as example) from the root directory you want to share:

```bash
> cd /path/to/my/pics
> python -m imageme
Processing .
Creating index file ./imageme.html
Processing ./photos
Creating index file ./photos/imageme.html
Processing ./photos/holiday
Creating index file ./photos/holiday/imageme.html
Processing ./photos/family
Creating index file ./photos/family/imageme.html
Processing ./super_secret_stay_out
Creating index file ./super_secret_stay_out/imageme.html
Your images are at http://127.0.0.1:8000/imageme.html
```

You can specify a port, just like you can with `SimpleHTTPServer` or `http.server`:

```bash
> python -m imagme 5678
Processing .
...
Your images are at http://127.0.0.1:5678/imageme.html
```

## Browse and Enjoy

Hit the URL imageMe tells you in your browser, and have fun exploring.
