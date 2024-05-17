## django darslar

### 24 dars
***Create login views***

templates/accounts/login.html
brinchi navbartda tizimga kirishi kerak bo'lgan foydalanovchilarni templates yani shablonini yaratib olamiz 
unada biz hardoyim html  formdan foydalanamiz...

```html
{% extends "base.html" %}

{% block contend %}
{% if error%}
   <h1 style="color:red">{{ error }}</h1>
{% elif %}
<duv style="margin-top:30px">
  <form method="POST" actions="">
  {% csrf_token %}
  <div>
    <input type="text" name="username" placeholder="username" />
  </div>
  <div>
    <input type="text" name="password" placeholder="passwors" />
  </div>
  <button type="submit"> Login</button>
  </form>
</div>
{%endblock %}
{% endif %}
```

users appga kiramiz

***user/views.py**

```python
from django.shortcuts import render
from django.contrib.auth import authenticate, login
#foydalanovchi tizimga kirishi
def loginViews(request):
    if request.method=="POST":
        username=request.POST.get("username")
        password=request.POST.get("password")
        print(username, password)
        user=authenticate(request, username=username, password=password)
        if user is None:
            context={"error": "siz ro'yhatdan o'tmagansiz"}
            return render(request, "accounts.html", context)
    return render(request, "accounts.html", {})
```
