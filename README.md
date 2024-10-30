## Casa&Cor

### :computer: [Project Link](https://casa-e-cor.vercel.app/)

---

#### Casa&Cor is a 100% professional responsive construction company website, featuring dark mode and 5 pages, built in HTML, LESS, and JavaScript, without using frameworks.

---

### :green_circle: Google Lighthouse - Mobile

![lighthouse_performance](https://github.com/tiagocreator/casa-e-cor/assets/82607849/f322d93c-2e16-4264-9a38-415ee415ca70)
![lighthouse_accessibility](https://github.com/tiagocreator/casa-e-cor/assets/82607849/19af3c74-197a-4ae3-9858-bf2604df7b41)
![lighthouse_seo](https://github.com/tiagocreator/casa-e-cor/assets/82607849/b6d214c6-f6cb-4d1d-83cb-236525377211)
![lighthouse_best-practices](https://github.com/tiagocreator/casa-e-cor/assets/82607849/3c2acd78-d8bd-4c1d-a9c3-fe40e84260e3)

---

### :sparkles: About the Site

This site uses the CSS preprocessor, LESS, to leverage its ability to perform CSS calculations for responsiveness. Since the __'em'__ units are based on the font size of their parent element, if the parent element doesn’t have a font size declared in its CSS, the next parent with a declared font size will be its base. Since I haven’t declared a font size on any container, everything on the page will look for a font size in the __'body'__ tag. We set a font size of __'20px'__, and the containers divide to get the value in __'em'__. So, I just set the font size in the __'body'__ tag to __'15px'__ on mobile devices, tablets, and small desktops up to __'1023px'__ wide. Then, at __'1024px'__, it’s set to __'20px'__.

---

### Explanation of Functionality

Each element's measurements that would be in pixels are now in __'ems'__ divided by 20 (the project's default font size). So, when we have an element with __'100px'__ width, we write it as __'100/20em'__ in the __'.less'__ file, and the compiler will render it in CSS as __'5em'__. Since the __'em'__ calculation is based on __'20px'__, changing the font size of the __'body'__ tag to __'15px'__ will shrink EVERYTHING because __'em'__ calculations are based on a smaller font size and will scale down proportionally.

For example, if an element has __'20px'__ width, it will be written as __'20/20em'__ in your __'.less'__ file and compiled to __'1em'__ in your __'.css'__ file. This is the proportion. When we change the __'body'__ tag font size (the main parent tag for everything) to a smaller number on mobile, say __'15px'__, we’re scaling the size of __'1em'__ to fit a font size based on __'15px'__ instead of __'20px'__. __'1em'__ would technically be __'15/15em'__, meaning that by reducing the font size of the __'body'__ tag by __'5px'__, everything that is based on its font size of __'20px'__ will also reduce by __'5px'__ in scale.

Both __'15/15'__ and __'20/20'__ instances result in __'1em'__. The parent’s base font size determines how large __'1em'__ is scaled up or down by default. Think of __'ems'__ as the measurement ratio to its parent font size, and the font size of the __'body'__ tag tells everything how large or small they should be overall. We set the proportion based on standard styles and measurements.

The larger the font size of the __'body'__ tag, the larger the __'1em'__ scale will be. Smaller font sizes decrease the __'1em'__ size. This is how we control mobile responsiveness. __This way, there's no need to write separate CSS styles for mobile and make larger sizes for the desktop__. By writing all __'css'__ properties' __'px'__ values as __'x/20em'__, everything will shrink on mobile and grow to its final scale size at the __'20px'__ font size.

For the project to work correctly and scale as it should, I used this __'.less'__ calculation system. So, if you have an __'h1'__ text that should be __'50px'__, you write it as __'50/20em'__. Just as I would normally. __However, any of its properties and children need to be divided by the newly declared font size__. So if there’s a bottom margin of __'20px'__, it will be __'20/50em'__, not __'20/20em'__, because the parent now has its own font size declared.


---

### How to Modify Project Styles and Use This System on Your Computer

1. I used the LESS preprocessor to take advantage of its calculation capabilities.

To install the LESS preprocessor, you should first download and install __npm__ so you can install any program with a single line of code.
After installing __npm__, install LESS with the following command in your terminal:

__npm install less__

2. I use the Koala app to compile LESS files to CSS, with a real-time auto-compilation function.

Here’s a link to download Koala:
http://koala-app.com/

Click on the __'+'__ icon and select the project’s __css__ folder to start the LESS to CSS compilation process. As long as the app is open, it will monitor and compile automatically.

![koala](https://user-images.githubusercontent.com/82607849/235378495-3ba4dced-2001-4dde-9e6a-3760eca83d2b.png)

---

### :notebook: License

Created and distributed under the __GPL v3__ license. See LICENSE.txt for more information.
  
---

### :handshake: Contributions

Contributions are what make the open-source community an amazing place to learn, get inspired, and create. Any contributions you make are greatly appreciated.

If you have a suggestion for improving the project, fork the repository and create a pull request. You can also simply open an issue with the "enhancement" tag. If you can, please star the project! Thank you.

---  

### Images

Home Page Light:

![home-light](https://github.com/tiagocreator/casa-e-cor/assets/82607849/228dffe4-b32d-461e-80c7-d08db6a27a2c)

Home Page Dark Mobile:

![home-dark-mobile](https://github.com/tiagocreator/casa-e-cor/assets/82607849/1599b5f3-cf55-4b18-ae14-bfc90150b963)

---

### :computer: [Project Link](https://casa-e-cor.vercel.app/)
