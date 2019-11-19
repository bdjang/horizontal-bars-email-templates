# Data Bars in Email Templates

* [Browsersync + Gulp.js](https://browsersync.io/docs/gulp)

## Background

A simple, straight-forward way to display data bars in email templates is by using `<td>` cells and the `background-color` property.

Why display data using HTML/CSS code instead of in an image? You can adjust HTML/CSS data for different screen sizes, data will automatically display when users open the email (not the case for images as some users have auto-loading images turned off in their email use of choice), and it's fun/challenging/and I'll respect you more for it.

```html
<table width="600">
  <tr>
    <td height="30" width="600" style="background-color: #0dbd67;"></td>
  </tr>
</table>
```

Adding additional `<td>` cells and adjusting the widths creates different sections within the data bar:

```html
<table width="600">
  <tr>
    <td height="30" width="200" style="background-color: #0dbd67;"></td>
    <td height="30" width="200" style="background-color: #86deb3;"></td>
    <td height="30" width="200" style="background-color: #dbdbdb;"></td>
  </tr>
</table>
```

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

Support for `<td>` cells and for these data bars is strong. Many email clients support this.