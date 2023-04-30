from PIL import Image, ImageDraw, ImageFont

# create a new image
image = Image.new(mode='RGB', size=(800, 800), color=(255, 255, 255))

# open the image of Lord Ram
ram_image = Image.open('ram.jpg')

# resize the Lord Ram image
ram_image = ram_image.resize((400, 400))

# paste the Lord Ram image onto the main image
image.paste(ram_image, (200, 50))

# add text to the image
draw = ImageDraw.Draw(image)
font = ImageFont.truetype('arial.ttf', size=50)
text = 'Shree Ram'
textwidth, textheight = draw.textsize(text, font)
x = (image.width - textwidth) / 2
y = 500
draw.text((x, y), text, font=font, fill=(0, 0, 0))

# save the image
image.save('shree_ram.jpg')
