Installer: http://cactuslab.com/imagemagick/
http://www.imagemagick.org/Usage/masking/#bg_remove

#Convert jpg into png and remove white background
/opt/ImageMagick/bin/convert alpha.jpg -bordercolor white -border 1x1 \
                    -alpha set -channel RGBA -fuzz 20% -fill none -floodfill +0+0 white \
                    -shave 1x1  alpha.png

#Crop images
/opt/ImageMagick/bin/convert 'Desktop/P*.jpeg' -crop '1653x2200+0+0' output/%02d.jpeg               