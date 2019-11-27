# Flask-Squeeze

Flask-Squeeze is a Flask extension that automatically:
- Minifies your JS and CSS files
- Compresses all HTTP responses with brotli
- Cachce static files so that they don't have to be recompressed

## Installation

`
    pip3 install Flask-Squeeze
`

## Usage

`
pyhton

    from flask_squeeze import Squeeze
    squeeze = Squeeze()

    # Initialize Extension
    squeeze.init_app(app)
`

Thats all!

## Options

You can configure Flask Squeeze with the following options:
- `COMPRESS_FLAG (default=True)`: Globally enables or disables Flask-Squeeze
- `COMPRESS_MIN_SIZE (default=500)`: Defines the minimum file size in bytes to activate the brotli compression
- `COMPRESS_LEVEL_STATIC (default=11)`: Possible value are 0 (lowest) to 11 (highest). Defines the compression level of brotli for files in static folders. Theses files fill also be cached, so that they only have to be compressed once. 
- `COMPRESS_LEVEL_DYNAMIC (default=5)`: Possible value are 0 (lowest) to 11 (highest). Defines the compression level of brotli for dynamic files like generated HTML files. Theses files will not be cached, so they will be compressed for each response.