# Ex.05 Design a Website for Server Side Processing
# Date:04/10/2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SERVER SIDE PROCESSING</title>
</head>
<style>
  body{
    background-image: url("{% static 'powerimg.png' %}");
    background-size:100% 100%;
    opacity: 0.7;
    background-position: center;
    background-repeat:no-repeat;
    justify-content: center; 
    align-items: center;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    position: relative;
  
  }

  .container{
    
    margin-top: 300px;
    margin-bottom: 500px;
    padding: 50px;
    max-width: 500px;
    max-height: 600px;
    border-radius: 20px;
    background-color: rgb(231, 231, 236);
  }

</style>

<body>
  <center>
    <form method="POST" class="container">

      <table>
        {% csrf_token %}

        <tr>
          <td>
            Intensity :

          </td>
          <td>
            <input type="text" name="Intensity" required>
          </td>
        <tr>


          <td>
            Resistance :
          </td>
          <td>
            <input type="text" name="Resistance" required>

          </td>
        </tr>

        <tr>
          <td>

          </td>
          <td>
            <button  >Calculate</button>
          </td>
        </tr>

        <tr>
          <td>
            <h3>
              Power = {{Power}}
            </h3>
          </td>

        </tr>
      </table>
    </form>

  </center>
</body>

</html>



views.py

from django.shortcuts import render


def maths_view(request):

    if request.method == 'POST':

        Intensity = float(request.POST.get("Intensity"))
        Resistance= float(request.POST.get("Resistance"))
        Pow = ((Intensity**2) * Resistance)
        print(f"Intenstiy={Intensity},Resistance={Resistance},Power= {Pow}")
        return render(request,'problem.html',{'Power': Pow})

    return render(request,'problem.html')  

urls.py
from django.contrib import admin
from django.urls import path
from formula import views  

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.maths_view),
]

```
# SERVER SIDE PROCESSING:
![alt text](<Screenshot 2025-10-04 124840.png>)
# HOMEPAGE:
![alt text](<Screenshot 2025-10-04 124826.png>)
# RESULT:
The program for performing server side processing is completed successfully.
