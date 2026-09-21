# Ex.No:07 JAVASCRIPT-BASED DRAWING APPLICATION
## Date:25.08.2026
## AIM

To develop a JavaScript-based drawing application using HTML5 Canvas to draw shapes such as Line, Rectangle, and Circle.

## ALGORITHM

1. Create an HTML page.
2. Add a `<canvas>` element to create the drawing area.
3. Add a drop-down list to select the shape (Line, Rectangle, or Circle).
4. Obtain the canvas context using `getContext("2d")`.
5. Capture the starting coordinates when the mouse button is pressed (`mousedown`).
6. Capture the ending coordinates when the mouse button is released (`mouseup`).
7. Determine the selected shape from the drop-down list.
8. Draw the selected shape:
   - Use `moveTo()` and `lineTo()` for a line.
   - Use `strokeRect()` for a rectangle.
   - Use `arc()` for a circle.
9. Display the drawn shape on the canvas.

## PROGRAM
```

<html>
    <head>
        <title>CANVAS</title>
    </head>
    <body>
    <h2>DRAWINGS</h2>
    <select id="shape" style="width:150px; height:35px; font-size:16px;">
        <option value="line">Line</option>
        <option value="rectangle">Rectangle</option> 
        <option value="circle">Circle</option>  
    </select>

    <br><br>
        
    <canvas id="canvas" width="600px" height="600px" style="border:2px solid black"></canvas>

    <script>
    
    let canvas=document.getElementById("canvas");
    let ctx=canvas.getContext("2d");

    let startX,startY;


    canvas.addEventListener("mousedown",function(e){
        startX=e.offsetX;
        startY=e.offsetY;
    });

    canvas.addEventListener("mouseup",function(e){
        let endX=e.offsetX;
        let endY=e.offsetY;

        let shape=document.getElementById("shape").value;
                
        if(shape=="line"){
            ctx.beginPath();
            ctx.moveTo(startX,startY);
            ctx.lineTo(endX,endY);
            ctx.stroke();
        }
            
        else if(shape=="rectangle"){
            
            ctx.strokeRect(startX,startY,endX-startX,endY-startY);

        }
        else if(shape=="circle"){
                    
            let radius=Math.sqrt(
            Math.pow(endX-startX,2)+
            Math.pow(endY-startY,2));

            ctx.beginPath();
            ctx.arc(startX,startY,radius,0,2*Math.PI);
            ctx.stroke();
        }
    });    

    </script>
        
    </body>

</html>
```


## OUTPUT

1.Line:

![alt text](image.png)

2.Rectangle:

![alt text](image-1.png)

3.Circle:

![alt text](image-2.png)


## RESULT

A JavaScript-based drawing application was successfully developed using HTML5 Canvas. The application enables users to draw Lines, Rectangles, and Circles interactively using mouse events.

