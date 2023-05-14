# Design a Website for Server Side Processing
AIM:
To design a website to perform mathematical calculations in server side.

DESIGN STEPS:
Step 1:
Clone the repository from GitHub

Step 2:
Create Django Admin project.

Step 3:
create a New App.

Step 4:
Create python programs for views and urls.

Step 5:
Create a HTML file of forms.

Step 6:
Publish the website in the given URL.

PROGRAM :
math.html

<title>Area of Rectangle</title> <style type="text/css"> body { background-color:red; } .edge { width: 1440px; margin-left: auto; margin-right: auto; padding-top: 250px; padding-left: 300px; } .box { display:block; border: Thick dashed lime; width: 500px; min-height: 300px; font-size: 20px; background-color:blue; } .formelt{ color:orange; text-align: center; margin-top: 7px; margin-bottom: 6px; } h1 { color:rgb(255, 0, 179); text-align: center; padding-top: 20px; } </style>
Area of a Rectangle
{% csrf_token %}
Length : (in m)
Breadth : (in m)

Area : m2
views.py

from django.shortcuts import render def rectarea(request): context={} context['area'] = "0" context['l'] = "0" context['b'] = "0" if request.method == 'POST': print("POST method is used") l = request.POST.get('length','0') b = request.POST.get('breadth','0') print('request=',request) print('Length=',l) print('Breadth=',b) area = int(l) * int(b) context['area'] = area context['l'] = l context['b'] = b print('Area=',area) return render(request,'myapp/math.html',context)

urls.py

from django.contrib import admin from django.urls import path from myapp import views urlpatterns=[ path('admin/',admin.site.urls), path('areaofrectangle/',views.rectarea,name="areaofrectangle"), path('',views.rectarea,name="areaofrectangleroot") ]

## OUTPUT:
![Screenshot (32)](https://github.com/BalaSathiesh/serversideprocessing/assets/128462891/0d332694-6688-428b-9dec-718253e2c953)
![Screenshot (33)](https://github.com/BalaSathiesh/serversideprocessing/assets/128462891/316c538a-c3eb-4a91-9d2a-0c048c673aa8)



## Result:
program excuted successfully
