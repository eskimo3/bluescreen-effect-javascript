image = new SimpleImage("a.jpg");
back = new SimpleImage("b.jpg");

for (pixel: image) {
  avg = (pixel.getRed() + pixel.getGreen() + pixel.getBlue())/3;
 
  if (pixel.getGreen() > avg * 1.05) {
    // 1. Get pixel2 from back image at same x,y (one line)
    pixel2 = back.getPixel(pixel.getX(), pixel.getY());

    // 2. Copy pixel2 over to pixel
    pixel.setRed(pixel2.getRed());
    pixel.setGreen(pixel2.getGreen());
    pixel.setBlue(pixel2.getBlue());
  }
}
print(image);
