# Data Bars in Email Templates

## Background

Using images is the most common way to display data in email templates. An alternative way to display data (in this case horizontal data bars) is laid out below. Here are some advantages of using this method of displaying data:

* Not all users have auto-loading images turned on in their preferred email clients. Data coded in HTML/CSS will be automatically display when the user opens the email.
* For email clients that allow it, hover states can add a level of interactivity to data bars in email templates.
* Data bars coded in HTML/CSS can be more readable and customized for mobile devices. Data in images are not mobile responsive - they can be difficult to view on mobile devices.

## Basics

By using `<td>` cells and the `background-color` property, you can display data bars in email templates.

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

### Adding interactive hover states

```css
<style type="text/css">
  .data1:hover {
    background-color: #3dca85 !important;
  }
  .data2:hover {
    background-color: #9ee4c2 !important;
  }
  .data3:hover {
    background-color: #e2e2e2 !important;
  }
</style>
```

```html
<table width="600">
  <tr>
    <td height="30" width="200" style="background-color: #0dbd67;" class="data1"></td>
    <td height="30" width="200" style="background-color: #86deb3;" class="data2"></td>
    <td height="30" width="200" style="background-color: #dbdbdb;" class="data3"></td>
  </tr>
</table>
```

### Adding a linear gradient

Adjusting the `background` property and the `linear-gradient` value

```html
<table width="600">
  <tr>
    <td height="30" width="350" style="background: linear-gradient(to right, #10ed81 0%, #0dbd67 100%); background-color: #0dbd67;"></td>
    <td height="30" width="250" style="background: linear-gradient(to right, #ffaa00 0%, #ff8300 100%); background-color: #ff8300;"></td>
  </tr>
</table>
```

![databar3](https://user-images.githubusercontent.com/6575035/69486223-895f9200-0e17-11ea-8458-e389413c2d17.png)

### Data labels

Adding labels and text inside the data bar or underneath it

```html
<table width="600">
  <tr>
    <td width="300" align="right" style="background: linear-gradient(to right, #10ed81 0%, #0dbd67 100%); background-color: #0dbd67; color: #000000; font-weight: 400; font-size: 14px; font-family: courier; line-height: 1.5em; margin: 0; padding: 0 6px 0 0;" height="31">Label</td>
    <td width="300" align="right" style="background: linear-gradient(to right, #ffaa00 0%, #FF8300 100%); background-color: #FF8300; color: #000000; font-weight: 400; font-size: 14px; font-family: courier; line-height: 1.5em; margin: 0; padding: 0 6px 0 0;" height="31">Label</td>
  </tr>
  <tr>
    <td align="right" valign="middle" width="300" style="color: #0dbd67; font-weight: 600; font-size: 16px; font-family: courier; line-height: 1.5em; margin: 0; padding: 2px 0 0 0;">$12,345.00</td>
    <td align="right" valign="middle" width="300" style="color: #FF8300; font-weight: 600; font-size: 16px; font-family: courier; line-height: 1.5em; margin: 0; padding: 2px 0 0 0;">$67,890.00</td>
  </tr>
</table>
```

![databar4](https://user-images.githubusercontent.com/6575035/69486225-91b7cd00-0e17-11ea-88fd-3ddc997db72f.png)

## Putting It All Together

By combining all the different variations, you can create informative, visually appealing, and mobile responsive data bars in email templates without relying on images.

![databar5](https://user-images.githubusercontent.com/6575035/69486240-d2174b00-0e17-11ea-824c-aa04b13a8195.png)