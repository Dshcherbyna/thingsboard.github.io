---
layout: docwithnav
assignees:
- ashvayka 
title: Advanced Data key configuration for a Chart Widget
description: Advanced data key Settings of the Chart Widget
  
---

* TOC
{:toc}

# Introduction

In the Advanced mode of the Data key you can configure such settings as 

Entering the Data key configuration window can be done in two ways, both of which you should start by clicking on the Pencil icon ("Enter edit mode") at the bottom right of the screen:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/chart-editmode-enter.png)
<br>
- If the Chart widget has already been created, and you’d like to set it up, you should click on the Pencil icon ("Edit widget") at the upper right corner of the widget:
  
![image](/images/user-guide/ui/widgets/chartwidget-advanced/enter-thechart.png)
<br>
- If you need to add a Chart widget, you can learn how to do it [here](/docs/getting-started-guides/helloworld/#step-34-add-chart-widget) and, 
  while creating, you are able to configure the data key by clicking the Pencil icon after adding the data key:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/create-chart-edit-key.png)

<br>
As soon as you got to the the Data key configuration, you need to choose the Advanced cell, and we can start adjusting:
<br>

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/chart-datakey-adv.png)

<br>
            
**Please note:** to apply any changes and see them in the widget, 
first, you need to Save them in the Data key configuration window, and then click on the orange checkmark at the upper right of the Edit window.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/apply-changes-datakey-adv.png)
<br>

# 1. Data key's visibility 

By default, most of the boxes are unchecked as it allows you to see more details about the Chart. 
Nevertheless, you have an opportunity to adjust and hide the information that you consider irrelevant.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/checkboxes-datakey-adv.png)

## 1.1. Data is hidden by default 

If the box _Data is hidden by default_ is checked, the data keys become invisible. 
You can notice that at the bottom of the widget, data keys, which have been just hidden, are crossed now.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/Data-hidden.png)

If you need to see the particular data key, you can click on the needed one and be able to see it on the Chart again.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/able-to-see-data.png)

**Please note:** You can manually hide/show data keys at any time by clicking the data key name at the bottom of the Chart widget.

## 1.2. Disable data hiding

As we learned from step 1.1., we can hide/show the required data by clicking the data key name at the bottom of the Chart widget.
If the box _Disable data hiding_ is checked, it becomes impossible to hide the data in the grid of the Chart widget.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/data-hide-imposs.png)

## 1.3. Remove datakey from legend

The Chart widget's got a legend which is shown at the bottom of the widget. 
By default, it consists of the data keys names on the bottom left and data keys' value on the bottom right.
If the box _Remove datakey from legend_ is checked, the information about the data keys is hidden.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/legend-is-hidden.png)

## 1.4. Exclude from stacking (available in "Stacking" mode)

In the advanced mode of the Chart widget itself, there is a Stack option that allows you to separate lines of data keys with the same values in the Chart. 
If the box _Exclude from stacking_ is checked, this particular data key line won't be stacked. 


## 1.5. Show lines

By default, this option is on, because it allows to see the data keys lines in the Chart widget.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/line-is-on.png)

If the box _Show lines_ is unchecked the appropriate data key line will be hidden in the Chart.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/line-is-off.png)


## 1.4. Fill lines

If the box _Fill lines_ is checked, the Chart widget will show the data key information as the filled-in space with the same color as the appropriate data key line.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/fill-lines.png)


## 1.5. Show points

If the box _Show points_ is checked, the Data key points always be displayed on the Chart widget.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/key-points-on.png)


# 2. Points 

Points are dots on the Chart widget that helps you to see particular moments of the data on the Chart widget. 

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/points-are.png)

## 2.1. Point shape

By default, the selected point shape is circle, but if you have a willing to custom it, you can easily do it by opening the drop-down menu. 


![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/change-shape-points.png)
<br>

After choosing the liked shape and saving the changes, we can see on the Chart widget that the points are changed.
![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/diamond-points.png)

In case you have ready shape format function for a point, you are able to input it into the following window:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/custom-function.png)

## 2.2. Line width of points

The value of _Line width of points_ value is responsible for the size of the point frame.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/linewidth-points.png)

For instance, let's set it to 1 and then to 10 to see the difference:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/1-10-width.png)

## 2.3. Radius of points

The _Radius of points_ line is responsible for the size of the points. As smaller the number, as smaller the point will be. 
Let's compare two cases: when the value of _Radius of points_ is set to 1 and to 10:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/radius.png)

## 2.4. Tooltip value format function, f(value)

A tooltip for points can be added by inputting the function for it in the window bellow.
For instance, you'd like to add the tooltip "hello" for your point. To achieve the needed result, you should input the following function into the 
_Tooltip value format function, f(value)_ window:

```text
return value + " hello";
```

After saving and applying the changes, the tooltip will appear after the point when you hover over it.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/tooltip-value-format-f.png)

<br>

Another good example of using this function would be: you have an automated doors, and you'd like to know either these doors opened or closed. 
You can learn this information with the following _Tooltip value format function_:

```text
return value ? "opened":"closed";
```

On the Chart widget you will see the answer on this question.

# 3. Axis

Axis settings allow you to adjust everything related to axis values, size, title, etc.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/axis.png)

## 3.1. Show separate axis

The checkbox _Show separate axis_ gives you an opportunity to differentiate values of axis on the Chart widget. 
In this particular example, there are two grid lines with two different values.
Therefore, if the checkbox is checked, the chart will look like this:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/separate-axis.png)

## 3.2. Values on the axis scale

By default, only the values that correspond to the indicators of the devices are shown on the Сhart. 
Setting the _minimum_ and _maximum values on the axis scale_ helps you adjust the Chart widget's scale to the size you want.
Let's look at the illustrative example: 
Our rates fluctuate from 25 degrees to 28 degrees, so the minimum and maximum values on Chart are exactly in this gap.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/no-max-min-value.png)
<br>

So now, if we set the _Minimum value on the axis scale_ to 1, and the _Maximum value on the axis scale_ to 50.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/max-min-value.png)
<br>

## 3.3. Axis Title 

To add a title to the Axis scale, you just need to enter the text in the _Axis Title_ line. After saving and applying changes, the Title for Axis appears on the Chart widget.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/axis-title.png)

## 3.4. Axis tick number of digits after floating point

By default, axis tick values are rounded to the full number. 
It is possible to change it by inputting the needed number of digits in the _Axis tick number of digits after floating point_ line. 
In our example, we had typed the number 5, and the _Axis tick number of digits after floating point_ has changed like this:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/digits-after-point.png)
<br>

## 3.4. Axis step size between ticks

On the Chart widget, the step size between ticks equals 1 by default.
To adjust the size of the step, you should enter the difference between the ticks number. In the example was entered 3. 

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/3-step-size.png)

## 3.5. Axis position

Axis position is always on the left side of the grid, until you change it in the drop-down menu _Axis position_ by clicking on the "Right" and saving the choice. 
After applying changes, the Chart widget with changed Axis position will look like this:

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/right-axis.png)

## 3.6. Ticks formatter function

To understand why do we need and how to use _Ticks formatter function_, let's use specific example.
Let's say we have telemetry that takes on very large numbers, and we need to build a small graph.
By default, the checkmarks on the vertical axis are quite long and take up most of the graph space, especially if there is a one next to the checkmark (in this case, "counts").

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/default-pic-ticks-function.png)

By using the ticks-formatter function we can convert the tick values into a more compact form.
Large numbers can be converted to this form:
       
**180,000,000,000 = 1.8 * 10 inches (+11 degrees) or 1.8e + 11**

```text
return value.toExponential(1) + "counts";
```

And we receive more compact result.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/compact-result-lol.png)

<br>

# 4. Thresholds

Thresholds can be used for personal control of the data's limits. 
There are two sources that you can choose from the drop-down menu for putting the thresholds on the Chart widget. 
You can do it by choosing:
- Predefined value (Default) - allows to adjust the thresholds in the Data key configuration window;
- Value taken from entity attribute - allows to adjust the thresholds in the separate window outside the Data key configuration window.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/treshold-datakey.png)

## 4.1. Predefined value (Default)

If you decided to use _Predefined value (Default)_ as the source, you should enter the value for a threshold. 
Since, in the example that we use, the data points are in between 25 and 28, let's put the threshold value to the 27. 
Then, necessarily we need to choose the color of the threshold line to make it visible, because it is transparent by default.
To make the threshold line more noticeable, we can adjust the _Line width_ by entering the digits in the appropriate line or with the help of the arrows on the left.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/threshold-predef.png)

After saving and applying the changes, the custom threshold line appears on the Chart widget.

![image](/images/user-guide/ui/widgets/chartwidget-advanced/datakey-cofigur-adv/threshold-predef-examp.png)

<br>


## 4.2 Value taken from entity attribute



# 5. Comparison Settings


