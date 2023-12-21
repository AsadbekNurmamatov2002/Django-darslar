# Django=5.0 -darslar
__mavzu:__ Django-templates-filter
__add__-Argumentni qiymatga qo'shadi.
>      {{ value|add:"2" }}
__capfirst__-Qiymatning birinchi belgisini bosh harf bilan yozadi. Agar birinchi belgi harf bo'lmasa, bu filtr hech qanday ta'sir qilmaydi.
>      {{ value|capfirst }}

__center__-Qiymatni berilgan kenglikdagi maydonga markazlashtiradi.
>    "{{ value|center:"15" }}"
__cut__-Berilgan satrdan arg ning barcha qiymatlarini olib tashlaydi.
>     {{ value|cut:" " }}
>
__date__
Sanani berilgan formatga muvofiq formatlaydi.
>      {{ value|date:"D d M Y" }}
>
__default__-Agar qiymat ga baholansa False, berilgan standartdan foydalanadi. Aks holda, qiymatdan foydalanadi.
>     {{ value|default:"nothing" }}
__dictsort__-Lug'atlar ro'yxatini oladi va argumentda berilgan kalit bo'yicha tartiblangan ro'yxatni qaytaradi.
>      {{ value|dictsort:"name" }}

>      {% for book in books|dictsort:"author.age" %}
>          {{ book.title }} ({{ book.author.name }})
>      {% endfor %}
__floatformat__
Argumentsiz foydalanilganda, suzuvchi nuqtali raqamni bitta kasrga yaxlitlaydi, lekin faqat o'nli qism ko'rsatilishi kerak.
>          value	          Shablon           	 Chiqish
>        34.23234	   {{ value|floatformat:3 }}  	34.232
>        34.23234 	{{ value|floatformat:"0" }}  	34
>        34.23234   {{ value|floatformat }}	      34.2

__lower__
Satrni barcha kichik harflarga aylantiradi.
>         {{ value|lower }}
__time__-Belgilangan formatga muvofiq vaqtni formatlaydi.
>          {{ value|time:"H:i" }}
__title__-So‘zlarni bosh harfdan, qolgan belgilarni esa kichik harfdan boshlash orqali satrni sarlavha harfiga o‘zgartiradi. Ushbu teg "arzimas so'zlarni" kichik harflarda saqlashga harakat qilmaydi.
__truncatechars__
Belgilar sonidan uzunroq bo'lsa, satrni qisqartiradi. Kesilgan satrlar tarjima qilinadigan ellips belgisi bilan tugaydi ("...").

Argument: kesish uchun belgilar soni
>        {{ value|truncatechars_html:7 }}
__truncatewords__-Ma'lum miqdordagi so'zlardan keyin qatorni qisqartiradi.
Argument: keyin qisqartiriladigan so'zlar soni
>           {{ value|truncatewords:2 }}
Agar valueshunday bo'lsa , chiqish bo'ladi ."Joel is a slug""Joel is …"
__truncatewords_html__-ga o'xshash truncatewords, faqat HTML teglaridan xabardor. Satrda ochilgan va kesish nuqtasidan oldin yopilmagan har qanday teglar kesilgandan so'ng darhol yopiladi.

Bu ga qaraganda unchalik samarali emas truncatewords, shuning uchun uni faqat HTML matni uzatilayotganda ishlatish kerak.
>            {{ value|truncatewords_html:2 }}
Agar valueshunday bo'lsa , chiqish bo'ladi ."<p>Joel is a slug</p>""<p>Joel is …</p>"
__urlencode__
URLda foydalanish uchun qiymatdan tashqariga chiqadi.

>     {{ value|urlencode }}
__upper__
Satrni barcha bosh harflarga aylantiradi.
{{ value|upper }}
