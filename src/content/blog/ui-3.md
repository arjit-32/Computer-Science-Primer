---
title: Mastering Core Design Principles
author: Arjit Sharma
date: 2024-10-02T05:00:00Z
courses: ["ui"]
categories: ["Product"]
featured: false
draft: false
---
Core design principles are the building blocks of effective UI/UX design. They ensure that digital interfaces are visually appealing, easy to navigate, and accessible. 

### Layouts

The layout defines how elements are arranged on a page to create a clear visual hierarchy and guide users through content effectively.
      
1. Add More Spacing - One of the easiest ways to clean up a design is to simply give every element a little more room to breathe. 
2. Having a base unit makes designing simple. Example is using 8px base unit - 8px 16px 24px 32px and so on. All UI elements should be measured in increments of our base unit.
3. A **Grid** is a framework used to arrange and align content and elements within a design, but do keep in mind that not everything in your layour is meant to be fluid. Take for example a sidenav.
4. Design for smaller devices first, then move to larger screens. Think in columns as well, something in smaller devices will have stacked columns but on larger screen can exist next to each other.
5. Relative sizing does’nt scale. Not every part of your interface has to be sized relative to one another ( shrinking one by 25%, also shrink other by 25%). 
Example - In first button even though proportions of font size and padding are preserved, but it gives more breathing space when we disproportionate padding for bigger font size.
6. You don’t always have to fill the whole screen, spreading our design to fill screen width will only make it look worse.

### Typography

Typography is all about techniques or arranging text to make written content readable and visually appealing. It innvolves selecting fonts type, style, spacing and laying it out to enhance user experience.  

1. About Typefaces and Fonts - 

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6ffd21e2-c246-4ea6-8879-c7b0b97bbb65/29193ea1-19ec-40c2-a2ac-54f204c7fc96/image.png)

- Serif - Traditional and Formal
- Sans Serif - Modern and Clean
- Monospaced should be used in technical places, where each character has same space.
- Display should be used for Headlines, Titles.
- Script are handwritten styles

1. Picking the right font
    
    Choosing right font is critical as it sets the tone of design, communicates emotions, and reinforces brand identity. Fonts evoke feelings and perceptions ( Ex - using a serious font in error message like Roboto ). Stick to 2 or 3 fonts for cohesive design. 
2. Establish  a Type Scale to avoid inconsistencies. 
In theory you would choose a modular scale (3:4-rounded or 2:3-perfect fifth or 1:1.618-golden ratio ) and a base value (16px) and then apply your ratio to get next values (16 → 16 * 1.618 = 25.8 .. ). In practice you need much more fonts, so hand choose your font sizes in advance ( without worrying about a formula ).  
    
    Example : 12px → 14px → 16px → 18px …
    
    Note - Also make sure to stick to *rem* or *px,*  because em units are relative hence will lead to inconsistencies.
3.   Keep your line length, line height and baselines in check

Line length refers to the width of a text block. Recommended length is 45-47 characters per line.

Baseline is the imaginary line where text sits, when using multiple fonts in 1 line, align it to baseline instead of vertical align for cleaner look.

Line Height is vertical spacing between lines, ideally set at 1.5, but is inversely proportional to font size ( For large text keep line height smaller ) 

![image.png](attachment:8b62d328-d4d9-4b17-bc3a-d6325773ada4:image.png)

4. Better to left align long form text and right align numbers.

![image.png](attachment:bf711767-4aee-47f4-8ca2-c8eb4c6e16a5:image.png)

![image.png](attachment:84ed1ee9-8551-426b-9594-f9d718e74776:image.png)

### Color

A well-chosen color palette enhances the visual appeal of an interface while improving usability and accessibility.

1. Color Theory Basics : Color theory is built on **primary colors** (red, blue, yellow), which mix to form **secondary colors** (green, orange, purple) and further blend to create **tertiary colors** (e.g., blue-green). 
The **color wheel** is a circular representation of these relationships, helping designers visualize complementary (opposite), analogous (adjacent), and monochromatic (variations of one color) schemes to achieve balance and contrast in their designs.

![image.png](attachment:ffcf8888-8c24-44df-887d-41474429ffc6:image.png)

2. Colors are represented in formats like **RGB** ( e.g., rgb(255,0,0) ), **HEX** (web-friendly, e.g., #FF0000), and **HSL** (intuitive for adjustments, e.g., hsl( e.g., hsl(0,50%,50%) ). Use **HEX/RGB** for digital, **HSL** for fine-tuning
3. You need way more colors than you think, so building a color palette involves extending main palette  to have multiple variations of same color. 
    
    Steps to remember while building a palette - 
    
- Primary colors of your site ( maybe 2 colors ), these determine overall look of the site.
- Accent colors that are eye-grabbing like yellow(for warnings), red(for dangers), green(for positive trends), pink or teal etc
- Have 8-10 shades of grey as they are used everywhere from texts to backgrounds and forms.
    
    ![image.png](attachment:13c083ef-491f-47fa-b9fc-667daf20e09d:image.png)
    

### Imagery and Iconography

Imagery, including **photos**, **illustrations**, and **icons**, enhances visual appeal and aids in communication. 

1. Text on Images - Text needs consistent contrast, a simple way to do this would be using a overlay. Other ways are to add are linear gradient, lower image contrast, colorize the image or add a text shadow.

![image.png](attachment:a1b2bd81-35d7-4815-ab61-8b2e868dd83d:6fdb8ca1-6c9f-4e77-a72f-bd15cc6eed53.png)

![image.png](attachment:0bd22b77-d4e3-42b2-b55f-64b77cc87525:image.png)

2. Icons should be **scalable** and **consistent**, avoiding excessive resizing that can distort clarity. **SVG** is the preferred format for sharpness and responsiveness, while **PNG** is suitable for fixed-size icons if optimized. 
    
    This is obvious but to re-iterate icons should follow a uniform **style** (e.g., filled, outlined).
    

### Accessibility

Accessibility ensures that digital interfaces are usable by everyone, including people with disabilities. It should be ingrained in the way we think. 

1. High color contrast (e.g., black text on a white background) improves readability, 
2. Larger touch targets (e.g., buttons at least 44x44px) help users with motor impairments. 
3. **Alt text for images** ensures screen readers can describe visuals, and **keyboard navigation** (e.g., using the Tab key to move between buttons) makes interactions smoother for users who can’t use a mouse. 
4. Adding **ARIA labels** to icons (e.g., `<button aria-label="Search">🔍</button>`) helps screen readers convey meaning.