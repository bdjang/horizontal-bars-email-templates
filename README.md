# Data Bars in Email Templates

## Background

Using images is the most common way to display data in email templates. One alternative way to display data is to code data bars in HTML/CSS. Here are some advantages of using this method:

* Some users have turned off auto-loading images in their preferred email clients. Data coded in HTML/CSS will display automatically when the user opens the email.
* If an image is replaced with data bars coded in HTML/CSS, the total email load time will be faster.
* Data bars coded in HTML/CSS can be more readable and customized for mobile devices. Data in images are not mobile responsive - they can be difficult to view on smaller screens.
* For email clients that allow it, hover states can add a level of interactivity to data bars in email templates.

## Basics

By using `<td>` cells and the `background-color` property, you can easily create a data bar in email.

```html
<table width="600">
  <tr>
    <td height="30" width="600" style="background-color: #0dbd67;"></td>
  </tr>
</table>
```

![databar1](https://user-images.githubusercontent.com/6575035/69486216-6fbe4a80-0e17-11ea-8858-14505fc43bc2.png)

Adding additional `<td>` cells and adjusting the widths will create different sections within the data bar:

```html
<table width="600">
  <tr>
    <td height="30" width="200" style="background-color: #0dbd67;"></td>
    <td height="30" width="200" style="background-color: #86deb3;"></td>
    <td height="30" width="200" style="background-color: #dbdbdb;"></td>
  </tr>
</table>
```

![databar2](https://user-images.githubusercontent.com/6575035/69486219-7c42a300-0e17-11ea-9635-f87b4a8acb1b.png)

## Customizing Data Bars

### Adding a linear gradient

Adjusting the `background` property and the `linear-gradient` value will create a smooth transition of colors in the data bars:

```html
<table width="600">
  <tr>
    <td height="30" width="350" style="background: linear-gradient(to right, #10ed81 0%, #0dbd67 100%);"></td>
    <td height="30" width="250" style="background: linear-gradient(to right, #ffaa00 0%, #ff8300 100%);"></td>
  </tr>
</table>
```

![databar3](https://user-images.githubusercontent.com/6575035/69486223-895f9200-0e17-11ea-8458-e389413c2d17.png)

For **Yahoo! Mail** and **Outlook.com** email clients, this CSS property does not work and the result will be a multi-colored data bar. For a fallback, add `background-color` after the `linear-gradient` which will display the data bar in one solid color.

```html
<table width="600">
  <tr>
    <td height="30" width="350" style="background: linear-gradient(to right, #10ed81 0%, #0dbd67 100%); background-color: #0dbd67;"></td>
    <td height="30" width="250" style="background: linear-gradient(to right, #ffaa00 0%, #ff8300 100%); background-color: #ff8300;"></td>
  </tr>
</table>
```

For **Outlook** email clients, you will need to use Vector Markup Language (VML) to achieve the linear-gradient look for these data bars.

```html
<!--[if mso]>
<v:shape coordorigin="0 0" coordsize="200 200" style="top:1;left:1;width:560;height:31" path="m 1,1 l 1,200, 200,200, 200,1 x e">
  <v:stroke opacity="0" />
  <v:fill type="gradient" color="#0dbd67" color2="#10ed81" angle="90" />
  <table width="560" border="0" cellspacing="0" cellpadding="0" style="width: 560px; height: 31px;">
    <tr>
      <td align="left"></td>
      <td align="right"></td>
    </tr>
  </table>
</v:shape>
<![endif]-->
```

You will need to add the `width` and `height` inline in the `table` element for Outlook DPI clients. This will allow the text for [data labels](https://github.com/bdjang/data-bars-email-templates#data-labels) to align correctly in the data bar.

### Adding interactive hover states

```css
<style type="text/css">
  .data1:hover {
    background: linear-gradient(to right, #10ed81 0%, #10ed81 100%) !important;
  }
  .data2:hover {
    background: linear-gradient(to right, #ffaa00 0%, #ffaa00 100%) !important;
  }
</style>
```

```html
<table width="600">
  <tr>
    <td height="30" width="350" style="background: linear-gradient(to right, #10ed81 0%, #0dbd67 100%); background-color: #0dbd67;" class="data1"></td>
    <td height="30" width="250" style="background: linear-gradient(to right, #ffaa00 0%, #ff8300 100%); background-color: #ff8300;" class="data2"></td>
  </tr>
</table>
```

![databar4](https://user-images.githubusercontent.com/6575035/69917960-2fc01e80-143a-11ea-8ab7-9438352ba921.gif)

### Data labels

You can add helpful information by including labels inside or underneath the data bars.

```html
<table width="600">
  <tr>
    <td width="300" align="right" style="background: linear-gradient(to right, #10ed81 0%, #0dbd67 100%); background-color: #0dbd67; color: #000000; font-weight: 400; font-size: 14px; font-family: courier; line-height: 1.5em; margin: 0; padding: 0 6px 0 0;" height="31">Label</td>
    <td width="300" align="right" style="background: linear-gradient(to right, #ffaa00 0%, #ff8300 100%); background-color: #ff8300; color: #000000; font-weight: 400; font-size: 14px; font-family: courier; line-height: 1.5em; margin: 0; padding: 0 6px 0 0;" height="31">Label</td>
  </tr>
  <tr>
    <td align="right" valign="middle" width="300" style="color: #0dbd67; font-weight: 600; font-size: 16px; font-family: courier; line-height: 1.5em; margin: 0; padding: 2px 0 0 0;">$12,345.00</td>
    <td align="right" valign="middle" width="300" style="color: #ff8300; font-weight: 600; font-size: 16px; font-family: courier; line-height: 1.5em; margin: 0; padding: 2px 0 0 0;">$67,890.00</td>
  </tr>
</table>
```

![databar5](https://user-images.githubusercontent.com/6575035/69486225-91b7cd00-0e17-11ea-88fd-3ddc997db72f.png)

## Putting It All Together

By combining all the different variations, you can create informative, visually appealing, and mobile responsive data bars in email templates without using images.

![databar6](https://user-images.githubusercontent.com/6575035/69486240-d2174b00-0e17-11ea-824c-aa04b13a8195.png)