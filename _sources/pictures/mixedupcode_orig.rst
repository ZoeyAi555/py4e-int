Mixed-Up Code Exercises
------------------------
.. parsonsprob:: mixedupcode_pictures_pp1
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``removeGreen`` that sets the green in all pixels in image ``kitten.jpg`` to 0. The function should return the image. 
	-----
	from image import *
	=====
	def removeGreen():
	=====
		img = Image('kitten.jpg')
	=====
		pixels = img.getPixels()
	=====
		for p in pixels:
	=====
			p.setGreen(0)
	=====
			img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
	=====
		win = ImageWin(img.getHeight(), img.getWidth()) #paired
	=====
		img.draw(win)
	=====
		return img
		
.. datafile:: kitten.jpg
	:image:
	:fromfile: Figures/kitten.jpg
	:hide:

.. activecode:: mixedupcode_pictures_ac1
	:practice: T
	:nocodelens:
	:datafile: kitten.jpg
	:autograde: unittest
	
	Write a function ``removeGreen`` that sets the green in all pixels in image ``kitten.jpg`` to 0. The function should return the image. 
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			g = removeGreen()
			pixels = g.getPixels()
			for p in pixels[0:2]:
				self.assertEqual(p.getGreen(), 0, 'Checking green in pixels were set to 0.')
	myTests().main()
		
	
.. parsonsprob:: mixedupcode_pictures_pp2
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``changeColors`` that for image ``beach.jpg`` sets the red in all pixels equal to the blue value. Then, it sets the green and blue in all pixels to 255.
	The function should return the image.
	-----
	from image import *
	=====
	def changeColors():
	=====
		img = Image("beach.jpg")
	=====
		pixels = img.getPixels()
	=====
		pixels = img.Pixels() #paired
	=====
		for p in pixels:
	=====
			b = p.getBlue()
	=====
			p.setRed(b)
			p.setGreen(255)
			p.setBlue(255)
	=====
			img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
	=====
		win = ImageWin(img.getHeight(), img.getWidth()) #paired
	=====
		img.draw(win)
	=====
		return img

.. datafile:: beach.jpg
	:image:
	:fromfile: Figures/beach.jpg
	:hide:

.. activecode:: mixedupcode_pictures_ac2
	:practice: T
	:nocodelens:
	:datafile: beach.jpg
	:autograde: unittest
	
	Write a function ``changeColors`` that for image ``beach.jpg`` sets the red in all pixels equal to the blue value. Then, it sets the green and blue in all pixels to 255.
	The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image('beach.jpg')
			pixels1 = img.getPixels()
			for p in pixels1[-1:]:
				x1 = p.getBlue()
		
			c = changeColors()
			pixels = c.getPixels()
			for p in pixels[-1:]:
				self.assertEqual(p.getRed(), x1, "Checking red pixels were set to blue.")
				self.assertEqual(p.getBlue(), 255, "Checking blue pixels were set to 255")
				self.assertEqual(p.getGreen(), 255, "Checking green pixels were set to 255")
	myTests().main()


.. parsonsprob:: mixedupcode_pictures_pp3
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``reduceGreen`` that reduces the green in all pixels by 75% in image ``kitten.jpg`` and returns the image.
	-----
	from image import *
	=====
	def reduceGreen():
	=====
		img = Image('kitten.jpg')
	=====
		pixelList = img.getPixels()
	=====
		pixelList = img.Pixels() #paired
	=====
		for p in pixelList:
	=====
			g = p.getGreen()
	=====
			p.setGreen(g * 0.25)
	=====
			p.setGreen(g * 0.75) #paired
	=====
			img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
	=====
		img.draw(win)
	=====
		return img

.. activecode:: mixedupcode_pictures_ac3
	:practice: T
	:nocodelens:
	:datafile: kitten.jpg
	:autograde: unittest
	
	Write a function ``reduceGreen`` that reduces the green in all pixels by 75% in image ``kitten.jpg`` and returns the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image('kitten.jpg')
			pixels1 = img.getPixels()
			for p in pixels1[:1]:
				x1 = p.getGreen() * 0.25
		
			c = reduceGreen()
			pixels = c.getPixels()
			for p in pixels[:1]:
				c1 = p.getGreen()
			self.assertEqual(c1, x1, "Checking that green pixels were reduced by 75%")
	myTests().main()

.. parsonsprob:: mixedupcode_pictures_pp4
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``changeRed`` that sets all red values equal to 1.5x the blue value in the image ``kitten.jpg``. The function should return the image.
	-----
	from image import *
	=====
	def changeRed():
	=====
		img = Image('kitten.jpg')
	=====
		pixels = img.getPixels()
	=====
		for p in pixels:
	=====
			r = p.getRed() #paired
	=====
			b = p.getBlue()
	=====
			p.setRed(b * 1.5)
	=====
			r.setRed(b * 1.5) #paired
	=====
			img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
	=====
		img.draw(win)
	=====
		return img

.. activecode:: mixedupcode_pictures_ac4
	:practice: T
	:nocodelens:
	:datafile: kitten.jpg
	:autograde: unittest
	
	Write a function ``changeRed`` that sets all red values equal to 1.5x the blue value in the image ``kitten.jpg``. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image('kitten.jpg')
			pixels1 = img.getPixels()
			for p in pixels1[:1]:
				x1 = p.getBlue() * 1.5
		
			c = changeRed()
			pixels = c.getPixels()
			for p in pixels[:1]:
				c1 = p.getRed()
				self.assertEqual(c1, x1, "Checking that red values were set to 1.5x the blue value")
	myTests().main()


.. parsonsprob:: mixedupcode_pictures_pp_5
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``modifyColors`` that decreases the red to 60% of its original value, increases the blue by 60% of its original value, and sets the green to 0 in the image ``beach.jpg``. The function should return the image.
	-----
	from image import *
	=====
	def modifyColors():
	=====
		img = Image("beach.jpg")
	=====
		pixels = img.getPixels()
	=====
		for p in pixels:
	=====
			r = p.getRed()
			b = p.getBlue()
	=====
			p.setRed(r * 0.6)
			p.setBlue(b * 1.6)
			p.setGreen(0)
	=====
			p.setRed(r / 0.6)
			p.setBlue(b * 0.6)
			p.setGreen(0) #paired
	=====
			img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
	=====
		img.draw(win)
	=====
		img.draw() #paired
	=====
		return img

.. activecode:: mixedupcode_pictures_ac5
	:practice: T
	:nocodelens:
	:datafile: beach.jpg
	:autograde: unittest
	
	Write a function ``modifyColors`` that decreases the red to 60% of its original value, increases the blue by 60% of its original value, and sets the green to 0 in the image ``beach.jpg``. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image("beach.jpg")
			pixels1 = img.getPixels()
			for p in pixels1[:1]:
				x1 = (p.getRed() * 0.6)
				x2 = (p.getBlue() * 1.6)
		
			c = modifyColors()
			pixels = c.getPixels()
			for p in pixels[:1]:
				c1 = p.getRed()
				c2 = p.getBlue()
				c3 = p.getGreen()
				self.assertEqual(1.2, x1, "Checking that red value was reduced to 60% of original value")
				self.assertEqual(1.6, x2, "Checking that blue value increased by 60% of original value")
				self.assertEqual(c3, 0, "Checking that green value was set to 0")
	myTests().main()

.. parsonsprob:: mixedupcode_pictures_pp6
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``imageToWhite`` that makes the image ``motorcycle.jpg`` completely white. The function should return the image.
	-----
	from image import *
	=====
	from picture import * #paired
	=====
	def imageToWhite():
	=====
		img = Image('motorcycle.jpg')
	=====
		pixels = img.getPixels()
		for p in pixels:
	=====
			p.setRed(255)
			p.setGreen(255)
			p.setBlue(255)
	=====
			p.setRed(0)
			p.setGreen(0)
			p.setBlue(0) #paired
	=====
			img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
		img.draw(win)
	=====
		return img


.. datafile:: motorcycle.jpg
	:image:
	:fromfile: Figures/motorcycle.jpg
	:hide:


.. activecode:: mixedupcode_pictures_ac6
	:practice: T
	:nocodelens:
	:datafile: motorcycle.jpg
	:autograde: unittest
	
	Write a function ``imageToWhite`` that makes the image ``motorcycle.jpg`` completely white. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image("motorcycle.jpg")
		
			i = imageToWhite()
			pixels = i.getPixels()
			for p in pixels[-1:]:
				r = p.getRed()
				b = p.getBlue()
				g = p.getGreen()
				self.assertEqual(r, 255, "Checking that the red value was set to 255")
				self.assertEqual(b, 255, "Checking that the blue value was set to 255")
				self.assertEqual(g, 255, "Checking that the green value was set to 255")
	myTests().main()


.. parsonsprob:: mixedupcode_pictures_pp_7
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``alternatingRed`` that sets the red of every other pixel to 0 in the image ``vangogh2.jpg``. The function should return the image.
	-----
	from image import *
	=====
	def alternatingRed():
	=====
		img = Image("vangogh2.jpg")
	=====
		for x in range(0, img.getWidth(), 2):
	=====
		for x in range(img.getWidth()): #paired
	=====
			for y in range(0, img.getHeight(), 2):
	=====
			for y in range(img.getHeight()): #paired
	=====
				p = img.getPixel(x,y)
	=====
				p.setRed(0)
	=====
				img.updatePixel(p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
		img.draw(win)
	=====
		return img

.. datafile:: vangogh2.jpg
	:image:
	:fromfile: Figures/vangogh.jpg
	:hide:

.. activecode:: mixedupcode_pictures_ac7
	:practice: T
	:nocodelens:
	:datafile: swan.jpg
	:autograde: unittest
	
	Write a function ``alternatingRed`` that sets the red of every other pixel to 0 in the image ``vangogh2.jpg``. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image("vangogh2.jpg")
			pixels_orig = img.getPixels()
			r_orig1 = img.getPixel(100,100).getRed()
			r_orig2 = img.getPixel(101,100).getRed()
				
		
			a = alternatingRed()
			r1 = a.getPixel(100,100).getRed()
			r2 = a.getPixel(101,100).getRed()
			self.assertEqual(r1, 0, "Checking that the values of the even elements have changed to zero")
			self.assertNotEqual(r_orig1, r1, "Checking that the values of the even elements have changed")
			self.assertEqual(r2, 40, "Checking that the values of the odd elements have stayed the same")
	
	myTests().main()


.. parsonsprob:: mixedupcode_pictures_pp8
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``changeQuadrantColors`` that only changes the color of the pixels in the bottom left quadrant of the image ``kitten.jpg``.
	The code should set the red value to the original blue value, the green value to the original red value, and the blue value to the original green value. The function should return the image.
	-----
	from image import *
	=====
	def changeQuadrantColors():
	=====
		img = Image("kitten.jpg")
	=====
		halfWidth = (int) (img.getWidth() / 2)
		halfHeight = (int) (img.getHeight() / 2)
	=====
		for x in range(halfWidth):
	=====
			for y in range(halfHeight, img.getHeight()):
	=====
			for y in range(halfHeight): #paired
	=====
				p = img.getPixel(x, y)
	=====
				r = p.getRed()
				g = p.getGreen()
				b = p.getBlue()
	=====
				newPixel = Pixel(b, r, g)
	=====
				img.setPixel(x, y, newPixel)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
		img.draw(win)
	=====
		return img


.. activecode:: mixedupcode_pictures_ac8
	:practice: T
	:nocodelens:
	:datafile: kitten.jpg
	:autograde: unittest
	
	Write a function ``changeQuadrantColors`` that only changes the color of the pixels in the bottom left quadrant of the image ``kitten.jpg``.
	The code should set the red value to the original blue value, the green value to the original red value, and the blue value to the original green value. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image("kitten.jpg")
			pixel_orig = img.getPixel(0,75)
			r_orig = pixel_orig.getRed()
			b_orig = pixel_orig.getBlue()
			g_orig = pixel_orig.getGreen()
				
		
			c = changeQuadrantColors()
			pixel_new = c.getPixel(0,75)
			r_new = pixel_new.getRed()
			b_new = pixel_new.getBlue()
			g_new = pixel_new.getGreen()
			self.assertEqual(r_new, b_orig, "Checking that the red values are set to original blue values")
			self.assertEqual(g_new, r_orig, "Checking that the green values are set to original red values")
			self.assertEqual(b_new, g_orig, "Checking that the blue values are set to original green values")
	myTests().main()

.. parsonsprob:: mixedupcode_pictures_pp9
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``copyRightSide`` that copies the right side of the image onto the left side in the image ``motorcycle.jpg``. The function should return the image.
	-----
	from image import *
	=====
	def copyRightSide():
	=====
		img = Image("motorcycle.jpg")
	=====
		halfway = (int) (img.getWidth() / 2)
	=====
		for x in range(halfway, img.getWidth()):
	=====
		for x in range(halfway): #paired
	=====
			for y in range(img.getHeight()):
	=====
				p = img.getPixel(x, y)
	=====
				img.setPixel(x - halfway, y, p)
	=====
				img.setPixel(halfway + x, y, p) #paired
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
		img.draw(win)
	=====
		return img


.. activecode:: mixedupcode_pictures_ac9
	:practice: T
	:nocodelens:
	:datafile: motorcycle.jpg
	:autograde: unittest
	
	Write a function ``copyRightSide`` that copies the right side of the image onto the left side in the image ``motorcycle.jpg``. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image("motorcycle.jpg")
			pixel_right = img.getPixel(195,50)
				
			c = copyRightSide()
			pixel_new = c.getPixel(97,50)
			self.assertEqual(list(pixel_right), list(pixel_new), "Checking that the right side of the image is copied onto the left side")
	myTests().main()

.. parsonsprob:: mixedupcode_pictures_pp10
	:numbered: left
	:practice: T
	:adaptive:

	Create a function ``copyTopQuarter`` that copies the pixels from the top quarter of the y-axis to the bottom quarter of the y-axis in the image ``vangogh2.jpg``. The function should return the image.
	-----
	from image import *
	=====
	def copyTopQuarter():
	=====
		img = Image("vangogh2.jpg")
	=====
		quarterHeight = (int) (img.getHeight() / 4)
	=====
		for x in range(img.getWidth()):
	=====
			for y in range(quarterHeight):
	=====
				p = img.getPixel(x, y)
	=====
				img.setPixel(x, quarterHeight * 3 + y, p)
	=====
		win = ImageWin(img.getWidth(), img.getHeight())
		img.draw(win)
	=====
		return img
	
.. activecode:: mixedupcode_pictures_ac10
	:practice: T
	:nocodelens:
	:datafile: vangogh2.jpg
	:autograde: unittest
	
	Write a function ``copyTopQuarter`` that copies the pixels from the top quarter of the y-axis to the bottom quarter of the y-axis in the image ``vangogh2.jpg``. The function should return the image.
	~~~~

	=====
	
	from unittest.gui import TestCaseGui
	
	class myTests(TestCaseGui):
		def testOne(self):
			img = Image("vangogh2.jpg")
			pixels1 = img.getPixel(0,0)
			pixels2 = img.getPixel(50, 50)
			pixels3 = img.getPixel(0,111)
			
				
			c = copyTopQuarter()
			pixels_new1 = c.getPixel(0,111)
			pixels_new2 = c.getPixel(50,50)
			self.assertEqual(list(pixels1), list(pixels_new1), "Check that the top quarter is copied to bottom quarter")
			self.assertEqual(list(pixels2), list(pixels_new2), "Checking that the pixels not in the bottom quarter stayed the same")
	myTests().main()
