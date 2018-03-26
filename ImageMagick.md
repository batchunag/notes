#Installer: 
http://cactuslab.com/imagemagick/
http://www.imagemagick.org/Usage/masking/#bg_remove

#Convert jpg into png and remove white background
/opt/ImageMagick/bin/convert alpha.jpg -bordercolor white -border 1x1 \
                    -alpha set -channel RGBA -fuzz 20% -fill none -floodfill +0+0 white \
                    -shave 1x1  alpha.png

#Crop images
/opt/ImageMagick/bin/convert 'Desktop/P*.jpeg' -crop '1653x2200+0+0' output/%02d.jpeg        
#Getting colorspace
identify -verbose image.jpg | grep "Colorspace:"       

#convert transparent png to white jpg
convert img23.png -size 480x320 xc:white +swap -compose over -composite img23.jpg

convert img23.png -background white -flatten img23.jpg

#Convert color-space
convert img23.jpg -colorspace CMYK img23_cmyk.jpg

#Get dominant color
convert $1 +dither -colors 2 -define histogram:unique-colors=true -format "%c" histogram:info: | awk -F'#' '{print $2}' | awk -F'FF' '{print $1}'