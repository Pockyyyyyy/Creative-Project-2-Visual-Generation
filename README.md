# Using Stable Diffusion to Generate Drinks Present Different Environment 

## Artist Statement
I have always had a passion for baking and combining my favorite plants into delicious desserts. The idea of this work is to take this a step further and use the real world environment as a source of inspiration by combining different colors and types of drinks to create a unique beverage that is representative of the natural world. With the help of Stable Diffusion (an AI image generator), I began to experiment with different cocktails and their bright colors to represent the different environments, such as a Blood Mary for a volcano and a mint mojito for streams and green leaves. However, I soon realized that I was limiting myself if I only used cocktails and so I decided to explore further and create drinks that were representative of different natural environments.
I take into consideration the iconic items that are found in each environment and use them to create a visual representation of the environment. For example, I used coconut trees and undersea to show the characteristics of the beach. And I didn't only use Stable Diffusion to generate the images, I also took the result into photoshop to create each drink poster to present these in a better way.
I do find the process of creating these drinks to be a creative challenge. Thinking about what elements should be in the enviroment and positioning all the items to make the drink looks good are the biggest challenges I was facing. The combination of the two interests allows me to create something that is unique and visually appealing. I believe that my work let people be able to appreciate the natural beauty of the environment shown in a form of a drink.

## Source Code
### There are several software been used in this project.

- Main tool to trained Stable Diffusion with my own images: [fast stable diffusion](https://github.com/Excalibro1/fast-stable-diffusionwik/wiki/fast-stable-diffusion-wiki).
- Main tool to generate images: [Stable Diffusion](https://github.com/Excalibro1/fast-stable-diffusionwik/wiki/fast-stable-diffusion-wiki)
- Tool to get the resource images for training: [Dream Studio](https://beta.dreamstudio.ai/generate)
- Tool to enhancer the quality/resolution of the generated image: [Remini Web](https://app.remini.ai/?v=e467d774-a97c-4b73-90e5-1d48a0f06930)
- Tool to edit the generated image into poster: [Photoshop](https://www.adobe.com/creativecloud/business/teams.html?sdid=B16P3W9X&mv=search&ef_id=Cj0KCQjww4-hBhCtARIsAC9gR3bmokijPb8wYO9-LLBbyA2m240hev7SDYtAde2J2HNNzxh50LfXmecaAtpxEALw_wcB:G:s&s_kwcid=AL!3085!3!566814725481!e!!g!!photoshop!15482932269!136265040448)

### Settings in Stable Diffusion

- txt2img:
Sampling method: Euler a
Sampling steps: 150
Width: 512
Height: 512
Others: Default

- img2img: Inpaint
Mask blur: 4
Mask mode: Inpaint masked
Masked content: latent noise
Inpaint area: Only masked
Only masked padding, pixels: 32
Sampling steps: 150
Others: Default

###prompts for each images:

1. Beach
text2img: isometric glass cup, isometric sparkling water in green blue
img2img Inpaint: beach pixel art with sea; coconut tree isometric; underwater pixel art

2. Rose Bush
text2img: isometric glass cup, cup of coke
img2img Inpaint: red rose in pixel art single; bush; thorns

3. Desert
text2img: isometric glass cup, blood mary
img2img Inpaint: desert; cactus isometric land; dragonfruit; tomato

4. Glacier
text2img: isometric glass cup, sparkling water
img2img Inpaint: glacier isometric land; rose in pixel art single; ice; snow mountain high

5. Lavender
text2img: isometric glass cup, grape juice
img2img Inpaint: lavender; lemon in slice; daisy in water pot

6. River
text2img: isometric glass cup, mojito
img2img Inpaint: lots of succulent; cactus isometric land; daisy in water pot; underwater pixel art

7. Swamp
text2img: isometric glass cup, green mojito
img2img Inpaint: mushroom trees; swamp underwater pixel art; moss

8. Universe
text2img: isometric glass cup, sparkling water
img2img Inpaint: starry sky with stars; lots cloud in sky; Mercury; Jupiter

9. Volcano
text2img: isometric glass cup, black tea
img2img Inpaint: lava isometric land; volcano isometric; amaranthus in red big

10. Wetlands
text2img: isometric glass cup, water
img2img Inpaint: mushroom trees; boat; stumps; rock ground


## Showcase Video

Short Video - [2 mins long slideshow](https://youtu.be/w6zcsLJW_Ig)
Long Video - [5 mins long explaining](https://youtu.be/QPHa0kNJTaU)

## Method

This project is done in several platforms/softwares. The steps will be list in numbers:

1. Before generating any images, training the AI image generator (Stable Diffusion) with special keywords and images is the very first step. I want my Stable Diffusion to learn everything about the enviroment and stuff I want to show in the enviroment. So I used **fast stable diffusion** to train my own image generator. 
2. I used **Dream Studio** as my resource image finder. Instead of finding low-resolution images on google, I chose **Dream Studio** to actually let it generate the images with the prompts I provide to get all in one-size (512 x 512) and high-resolution images. For example, I want all my drinks and resources are in isometric, I used isometric, mojito, pixel art, hyper details as my prompt to generate some images I can use to train my own stable diffusion. So it's kind of interesting that I'm using a result from an AI image generator to train another AI image generator.
3. After I got all my images, I have to rename the same type into the same names (the keyword I will later use to generate as prompt) with sorting numbers, for example, mojito(1), mojito(2), mojito(3) and etc.
4. Then I will start on my **fast stable diffusion** on Google Colab and create my session a name (project2pocky) in Create/Load a Session section, and then upload all my images in the Instance Images section. After it uploads all the images, the training begins. I set it to **3000 UNet Training Steps, with 2e-6 Learning Rate, and 350 Text Encoder Training Steps, 1e-6 Text Encoder Learning Rate**. After it's trained, I can test the trained model and start my trip. I noticed it will be really helpful if you name the images to special names that the basic model doesn't have these keywords in. When you generate the image, it will know exactly what you want.
5. For the generate part, I will first use simple prompts to generate from text to image, and then put the image I feel it's good into img2img Inpaint. I will erase some of the parts and use different prompts to put the items I want on the image. I spent most of my time on this step. Usually, an image took about 1-2 hours to get a result I like. I did download about 200 images to make 10 static images.
6. After I download the result I like, I will put it on **Remini Web** to have the image in a higher resolution.
7. Then I will put the image into photoshop and cut off the background of the image. And use the colors from the image to make a poster that present the drinks in a better way.
