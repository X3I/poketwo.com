<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
 <title>Table with vertical scroll HTML</title>

 <style type="text/css">
table#header {
 background-color: lightgrey;
 width: 230px;
}
table#header th {
 width: 100px;
}
table#header th+th {
 width: 120px;
}
div#scroller {
 height: 100px;
 width: 230px;
}
table#data {
 background-color: lightyellow;
 width: 200px;
}
table#data td {
 border-bottom: 1px solid lightgrey;
}
table#data td > span {
 display: inline-block;
 overflow: hidden;
 white-space: nowrap;
 width: 100px;
}
 </style>
</head>

<body>
 <div>
  <table id="header">
   <tr>
    <th>Item name</th>
    <th>Amount</th>
   </tr>
  </table>
 </div>
 <div id="scroller" style="overflow:auto;">
  <table id="data">
   <tr>
    <td><span>Item with very long dummy title</span></td>
    <td><span>10000</span></td>
   </tr>
   <tr>
    <td><span>Simple wheel</td>
    <td><span>100</span></td>
   </tr>
   <tr>
    <td><span>Apple</span></td>
    <td><span>1</span></td>
   </tr>
   <tr>
    <td><span>Pineapple</span></td>
    <td><span>2</span></td>
   </tr>
   <tr>
    <td><span>Strawberry</span></td>
    <td><span>10</span></td>
   </tr>
   <tr>
    <td><span>Spoon</span></td>
    <td><span>500</span></td>
   </tr>
   <tr>
     <td><span>Knife</span></td>
     <td><span>100</span></td>
    </tr>
    <tr>
     <td><span>Cup</span></td>
     <td><span>20</span></td>
    </tr>
    <tr>
     <td><span>Killing sphere</span></td>
     <td><span>576</span></td>
    </tr>
    <tr>
     <td><span>Little ball</span></td>
     <td><span>30</span></td>
    </tr>
   </table>
  </div>
 </body>

</html>
