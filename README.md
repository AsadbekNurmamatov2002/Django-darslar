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


## _demak misollarga o'tamiz__
__1-qadam__   Django - Virtual muhit yaratish va Djangoni o'rnatamiz
>       py -m venv myen
>       myworld\Scripts\activate.bat
>       py -m pip install Django
>       django-admin --version
>       5.0
>       django-admin startproject myproject
>       cd myproject
>       py manage.py runserver
>       CTRL+C
>       py manage.py startapp myfilter
>       code .
__2-qadam__ Django- loyihamizni+ ilavalarimizbilan birlashtiramiz (project+app)
__settings.py__ appni qo'shqmiz
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/d46d4bfe-b27f-4c3f-813e-cd2c19cec3a6)
__urls.py__ app dage urls.py ni ko'rsatib qo'yishimiz kerak
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/7cb8b04b-ec9d-482f-bae6-bf5e6996ee7d)
__myfilter/urls.py__ views.py dagi Home funcsiyamizni ko'rsatamiz
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/c04102af-423d-4fa9-8b26-7df963746d1a)
__3-qadam__ views.py quydagilarni qo'shamiz
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/c2eebe2d-7efc-4904-b151-4c76a632d4db)

__4-qadam__ template __home.html_ 
settins.py ga templates fileni qo'shing
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/b57d9a41-13ee-4863-b867-a7156008e767)
views.py ga quydagilarni yozamiz
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/9fdb15f9-0300-4e4b-8fe3-13d1c5c1be02)

![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/0e6aa955-72bd-49db-8b48-25874473152c)


# Django bilan tanishtirish
>  Umumiy koʻrinish
Django yuqori darajadagi Python veb-ramka bo'lib, xavfsiz va xizmat ko'rsatish mumkin bo'lgan veb-saytlarni tez rivojlantirish imkonini beradi. Bu bepul va ochiq manba. U to'liq stekli ilovalarni ishlab chiqish va serverlarni ishlab chiqish uchun ishlatiladi. Django frontend bilan bir qatorda backend uchun ham mos keladi. Bu Python kutubxonalarining to'plami bo'lib, u bizga backend va frontend maqsadlari uchun ideal bo'lgan foydali veb-ilovalarni ishlab chiqish imkonini beradi.

## __Django bilan tanishtirish_

Internet hayotimizning muhim qismiga aylandi va veb-saytlar ham. Django Python bilan birgalikda dinamik veb-saytlarni ishlab chiqishda yordam beradi. Endi siz dinamik veb-sayt nima ekanligini qiziqtirgan bo'lsangiz kerak, bu vaqti-vaqti bilan mazmuni o'zgarib turadigan veb-sayt. Xo'sh, Django nima? Django - bu to'liq stekli ilovalarni ishlab chiqish va serverlarni ishlab chiqish uchun ishlatiladigan yuqori darajadagi Python veb-ramka. Kirish tizimi, ma'lumotlar bazasiga ulanish va CRUD operatsiyasi kabi xususiyatlar bilan Django ilova yaratishni osonlashtiradi. Django veb-ishlab chiqishdagi ko'p mashaqqatlarni hal qiladi, bu sizga ilovangizni yozishga e'tiboringizni qaratish imkonini beradi. Django - bu ochiq manbali ramka, Djangoning GitHub ombori har oy 2000 dan ortiq hissalarni oladi. Uning keng moslashuvchanligi va ochiq manba tabiati uni doimiy ravishda rivojlanib boruvchi asosga aylantiradi. Muammoga duch kelgan dasturchilar Internetdagi faol hamjamiyat tufayli yechimlarni osongina topishlari mumkin.

## __Django xususiyatlari_
Djangoning ba'zi xususiyatlari:

SEO optimallashtirilgan: Qidiruv tizimini optimallashtirish qidiruv tizimiga veb-saytlarni qo'shmoqda, shunda u eng yaxshi natijalarda paydo bo'ladi. Qidiruv mexanizmlari ba'zi algoritmlardan foydalanadi, ular ba'zan veb-ishlab chiquvchi bilan ko'p hamkorlik qilmaydi. Biz veb-saytimizni odamlarga tushunarli shaklda yaratmoqdamiz va ular qidiruv tizimi tomonidan tan olinishi uchun uni serverdagi URL shaklida qo'shishlari kerak. Django veb-saytni serverning IP manzili emas, balki URL manzillari orqali boshqarganligi sababli, muhandisga veb-saytni serverga qo'shishni osonlashtiradi va URLni raqamli kodga aylantirish shart emas.

__Yuqori miqyoslilik:__ Django ishlab chiquvchilar tomonidan yaratilganidan boshqa Python kutubxonasidan foydalanmaydi. Bu Django-ni hamma uchun xatosiz kengaytiriladigan veb-saytlar yaratish uchun ideal qiladi.

__Xavfsiz :__ Django xavfsizlikni afzal ko'radi va ishlab chiquvchilarga SQL in'ektsiyasi, saytlararo skriptlar va boshqalar kabi keng tarqalgan xavfsizlik kamchiliklarini oldini olishda yordam beradi. Uning foydalanuvchi autentifikatsiya tizimi foydalanuvchi hisoblari va parollarini xavfsiz boshqarish imkonini beradi.

__Ko'p qirrali:__ Djangoning ko'p qirraliligi unga keng doiradagi domenlar uchun ilovalar yaratish imkonini beradi. Hozirda kompaniyalar Django-dan kontentni boshqarish tizimlari, ijtimoiy tarmoq saytlari va ilmiy hisoblash platformalari kabi turli xil ilovalarni yaratishda foydalanmoqda.

__Portativ:__ Django portativ ramka bo'lib, uning kodi har qanday platformada, jumladan, kompyuter, Mac, Windows va Linuxda ishlashi mumkin. Ushbu ramkaning platformalararo tabiati ishlab chiquvchilarga barcha ishlab chiqish va ishlab chiqarish muhitlarini qo'llab-quvvatlash imkonini beradi.

__Tez rivojlanish:__ Ushbu ramka dasturni yaratish jarayonini kodni noldan yozmasdan oson va tezroq qiladi. Ma'lumotlar bazasini loyihalash va ulanish uchun alohida server fayllarini yaratish va serverga va serverdan ma'lumotlarni uzatish uchun boshqa fayl yaratishga hojat yo'q. Django bu ishni va boshqa ba'zi vazifalarni ham bajaradi. Django qulaylikni ta'minlaydi va murakkab va ma'lumotlarga asoslangan veb-saytlarni ishlab chiqishni ancha osonlashtiradi.

## __Django tarixi_
Django 2003 yilda Lawrence Journal World Newspaper veb-ishlab chiquvchilari Arian Holovaty va Simon Willison tomonidan ishlab chiqilgan . Adrian Xolovati ushbu veb-ramkani mashhur jazz gitaristi Django Reynxard sharafiga nomladi. U 2005 yil iyul oyida BSD litsenziyasi ostida ommaga chiqarildi . Hozirgi vaqtda DSF (Django Software Foundation) o'zining ishlab chiqish va chiqarish tsiklini davom ettirmoqda.

## __Django qanchalik mashhur?_
Django - bu juda mashhur ramka. Washington Post Django yordamida har daqiqada tirbandlikni boshqaradi. Django-dan yordam beruvchi boshqa mashhur yangiliklar ilovalari va ijtimoiy ilovalar: The New York Times, The Onion, The Guardian, Instagram va Youtube. Ulardan tashqari, National Geographic, NASA va boshqalar kabi boshqa ta'lim veb-saytlari.

## __Django qanday ishlaydi?__
Django model ko'rinishi shablonining me'moriy naqshiga amal qiladi:

__Model :__ Bu saqlangan ma'lumotlarning tuzilishi, jumladan maydon turlari, ularning maksimal hajmi, standart qiymatlari va boshqalar sifatida aniqlanadi. Har bir model bitta ma'lumotlar bazasi jadvaliga mos keladi.
__Shablon :__ U ma'lumotlarni taqdim etish bilan shug'ullanadi.
__Ko'rish :__ Bu odatda HTML, CSS yoki Javascript fayllari bilan ifodalanadigan foydalanuvchiga ko'rsatiladigan mantiqni o'z ichiga olgan komponent.

## __Django kodi nimaga o'xshaydi?_
Xo'sh, siz Django kodi qanday ko'rinishini qiziqtirgan bo'lsangiz kerak. Keling, misol keltiramiz va mahsulotlar, mijozlar va xarid savatchasi ilovalari bilan onlayn do'kon nomli loyihani yaratamiz. Django kodlari uni tizimimizga o'rnatganimizdan so'ng darhol buyruq satrida yoki Windows Powershell-da yoziladi.

Dastlab biz virtualenv venv yordamida virtual muhitga kiramiz va kodning dastlabki ikki satrida venv\scripts\activate yordamida uni faollashtiramiz.
Virtual muhitni faollashtirgandan so'ng, biz django-admin startproject OnlineShop kodidan foydalanib loyihani boshlaymiz .
Nihoyat, ilovani python manage.py startapp Products bilan ishga tushiring


![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/5ee8a1c9-1d38-45e5-9f43-52f564e9ec09)

__Model__
Djangodagi model ma'lumotlarni saqlash usulidir. Masalan , mahsulotlar ilovasi ostidagi model.py- da biz mahsulot nomi, mahsulot narxi va miqdori kabi mahsulotlarning tarkibiy qismlari bilan shug'ullanamiz. Django kodni ma'lumotlar bilan bog'lash uchun ORM (Ob'ekt bilan bog'liq xaritalash) dan foydalanadi. Shunday qilib, Django bizga ORM deb nomlangan API yordamida o'zining ma'lumotlar bazasi modellari, ya'ni kiritish, o'zgartirish, o'chirish va hokazolar bilan o'zaro aloqa qilish imkonini beradi. U SQLite, PostgreSQL va MySQL kabi turli relyatsion ma'lumotlar bazalari ma'lumotlari bilan o'zaro ishlash uchun ishlatiladi. Odatda, har bir model bitta ma'lumotlar bazasi jadvaliga mos keladi. Har bir model django.db.models.Model ning pastki sinfi bo'lgan Python sinfidir.

Qo'shimcha tushuntirish uchun misol bo'limiga qarang.

![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/29cc345e-a894-4ee7-b8ad-bd395d4bb02c)
__Ko'rinish__
Ko'rinish model va shablonlar o'rtasidagi bog'lovchi vazifasini bajaradi. U foydalanuvchi so'rovini qabul qiladi, ma'lumotlar bazasidan tegishli ma'lumotlarni oladi, so'ngra olingan ma'lumotlar bilan birga shablonni qaytaradi. View funksiyalarini views.py faylida yozamiz . Ushbu funktsiyada biz har bir HTML faylni bog'laymiz. Biz urls.py da mavjud urlpatternlardagi URL manzillari yordamida ma'lum bir ko'rinishni chaqiramiz . Iltimos, misol bo'limiga qarang.


![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/d0b2aa8e-64ad-4e8f-b3b1-cd4ccc0ba3fc)

__URL marshrutlash__
U URL manzillarini bog'laydi va shablonlarni ko'rsatadi. Ichki loyiha papkasining urls.py faylida u view funksiyasini views.py dan urls.py ga import qiladi .

![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/0e8c06b4-165e-468f-804d-2b2c397f2240)

__Shablon__
Tashqi loyiha papkasida shablon nomli papka yaratilishi kerak va barcha HTML fayllar unda saqlanadi. Loyihaning ichki papkasida joylashgan settings.py faylida shablon nomi TEMPLATES ostidagi DIRS sozlamalariga qo'shiladi.

![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/08cb91ec-44e3-4cdb-9d75-6e652e70a87a)

![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/f8878a76-9125-4684-b2ac-ad6b144bb85c)
- views.py faylida soʻrovni boshqarish : Ushbu kodda biz def first(request) koʻrish funksiyasini yaratmoqdamiz : HTML sahifasini sahifa1.HTML bilan biz yaratgan “birinchi” funksiya bilan bogʻlash uchun.
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/e86ee3ef-df82-45f6-9111-7f5d574f254e)
- models.py da ma'lumotlar modellarini aniqlash: Models.py fayli har bir ilova papkasida mavjud. Ushbu kod ostida biz mahsulot nomini belgi sifatida, narxni suzuvchi qiymat sifatida va miqdorni butun son sifatida qabul qilish orqali Mahsulot ilovasi ma'lumotlarini bog'laymiz.
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/c0b7689e-abfe-43ec-8bdd-a63bc6056e0b)
>   Xulosa
Salom dasturchi! Ishonchim komilki, siz Django nima haqida tasavvurga ega bo'lsangiz kerak. Keling, ushbu maqoladan nimani o'rganganimizni umumlashtiramiz

Django ilovalarni ishlab chiqish uchun Python veb-ramkasidir.

Bu xavfsiz, ko'p qirrali, portativ va parvarish qilish oson.

U MVT (model, shablon, ko'rinish) me'moriy naqshiga amal qiladi.


![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/ed515d0e-0961-4390-ae4c-2996cb93f589)

__on_delete = models.CASCADE__ : Bu standart sozlama. U modeldagi yozuv o'chirilganda bog'langan modeldagi barcha tegishli yozuvlar ham o'chirilishini ta'minlaydi.
__on_delete = models.PROTECT__ : Boshqa yozuvlar bilan aloqasi bo'lgan yozuvni o'chirish bloklanishini ta'minlaydi.
__on_delete = models.SET_NULL__ : Yozuv o'chirilganda, agar null = True o'rnatilgan bo'lsa, u relyatsion maydonga NULLni tayinlaydi.
__on_delete = models.SET_DEFAULT__ : Yozuv oʻchirilganda va birlamchi qiymat berilishi kerak boʻlganda aloqador maydonlarga standart qiymatlarni beradi.
__on_delete = models.SET()__ : Qaytish qiymati maydonga tayinlangan parametr yoki chaqiriladigan qiymat sifatida standart qiymatni olish uchun ishlatilishi mumkin.
__on_delete = models.DO_NOTHING__ : Hech narsa qilmaydi. Hech qanday chora ko'rilmaydi.


# Django Session foydalanish
Django anonim va foydalanuvchi __Session__ qo'llab-quvvatlaydigan __Session__ ramkasini taqdim etadi. __Session__ ramkasi ishi har bir tashrif buyuruvchi uchun o'zboshimchalik bilan ma'lumotlarni saqlash imkonini beradi. __Session__ ma'lumotlari server tomonida saqlanadi va
cookie-fayllarga asoslangan seans mexanizmidan foydalanmasangiz, cookie-fayllar sessiya identifikatorini o'z ichiga oladi. Seans o'rta dasturi
cookie fayllarini yuborish va qabul qilishni boshqaradi. Odatiy __Session__ mexanizmi __Session__ ma'lumotlarini ushbu faylda saqlaydi
ma'lumotlar bazasi, lekin siz boshqa __Session__ dvigatellarini tanlashingiz mumkin.
__Session__ dan foydalanish uchun loyihangizning MIDDLEWARE sozlamasida “django” mavjudligiga ishonch hosil qilishingiz kerak.
__'django.contrib.sessions.middleware.SessionMiddleware'.__ Ushbu o'rta dastur __Session__ boshqaradi. Qo'shilgan
startproject buyrug'i yordamida yangi loyiha yaratishda sukut bo'yicha MIDDLEWARE sozlamasiga
__Session__ ning o'rta dasturi joriy sessiyani so'rov ob'ektida mavjud qiladi. 

>
Foydalanuvchilar saytga kirganda, ularning anonim __Session__ yo'qoladi va yangi __Session__ yaratiladi
autentifikatsiya qilingan foydalanuvchilar uchun. Agar siz saqlashingiz kerak bo'lgan narsalarni anonim __Session__ saqlasangiz
foydalanuvchi tizimga kirgandan so'ng, eski __Session__ ma'lumotlarini yangi __Session__ nusxalashingiz kerak bo'ladi. Siz
login() yordamida foydalanuvchi tizimga kirishdan oldin __Session__ maʼlumotlarini olish orqali buni amalga oshirishi mumkin.
Django autentifikatsiya tizimining funksiyasi va undan keyin uni __Session__ da saqlash
>

__Session__ sozlamalari
Loyihangiz uchun  __Session__ larni sozlash uchun foydalanishingiz mumkin bo'lgan bir nechta sozlamalar mavjud. Eng muhimi
__SESSION_ENGINE__. Ushbu sozlama __Session__ lar saqlanadigan joyni belgilash imkonini beradi. Odatiy bo'lib, Django
__Session__ larni __django.contrib.sessions__ ilovasining __Session__ modeli yordamida ma'lumotlar bazasida saqlaydi.
Savdo aravachalarini seanslarda saqlash
Seansda savat elementlarini saqlash uchun JSONga ketma-ketlashtirilishi mumkin bo'lgan oddiy tuzilmani yaratishingiz kerak.
Savatda har bir element uchun quyidagi ma'lumotlar bo'lishi kerak:
* Mahsulot namunasining identifikatori
* Mahsulot uchun tanlangan miqdor
* Mahsulot birligi narxi
Mahsulot narxi har xil bo'lishi mumkinligi sababli, keling, mahsulot narxini saqlash usulini ko'rib chiqaylik
mahsulot savatga qo'shilganda o'zi. Shunday qilib, siz mahsulotning joriy narxidan foydalanasiz
foydalanuvchilar uni o'z savatiga qo'shishadi, mahsulot narxi keyinchalik o'zgartiriladimi yoki yo'qmi. Buning ma'nosi
mijoz uni savatga qo'shganda buyumning narxi ushbu mijoz uchun saqlanadi
to'lov tugaguncha yoki session tugaguniga qadar.
Keyinchalik, xarid qilish aravachalarini yaratish va ularni seanslar bilan bog'lash uchun funksionallikni yaratishingiz kerak. Bu
quyidagicha ishlashi kerak:
* Arava kerak bo'lganda, maxsus session kaliti o'rnatilganligini tekshirasiz. Agar arava o'rnatilmagan bo'lsa sessiyada siz yangi savat yaratasiz va uni savat seansi kalitida saqlaysiz.
* Ketma-ket so'rovlar uchun siz xuddi shu tekshiruvni bajarasiz va savatdagi narsalarni aravadan olasiz seans kaliti. Seansdan savat elementlarini va ularga tegishli Mahsulob'ektlarini olasiz
ma'lumotlar bazasidan

Loyihangizning settings.py faylini tahrirlang va unga quyidagi sozlamani qo'shing
>     CART_SESSION_ID = 'cart'
Bu aravani foydalanuvchi session saqlash uchun foydalanmoqchi bo'lgan kalit. Chunki Django session alari
har bir tashrifchi uchun boshqariladi, siz barcha seanslar uchun bir xil savat session i kalitidan foydalanishingiz mumkin.
Keling, xarid qilish aravachalarini boshqarish uchun dastur yarataylik. Terminalni oching va loyiha katalogidan quyidagi buyruqni bajarib, yangi dastur yarating:
>     python manage.py startapp cart
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/7c5b6218-faad-4fa1-a126-c64657eaa877)

Savat ilovalari katalogida yangi fayl yarating va uni cart.py deb nomlang. Unga quyidagi kodni qo'shing:
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/645d87d1-f088-4cb1-9152-d7fc514af261)
Bu xarid qilish savatini boshqarish imkonini beruvchi Cart sinfidir. Siz savatni so'rov obyekti bilan moslashtirishni talab qilasiz. Siz self.session = request.session yordamida joriy seansni saqlaysiz
Cart sinfining boshqa usullariga kirish uchun.
Birinchidan,  __self.session.get(settings.CART_SESSION_ID)__  yordamida joriy seansdan savat olishga harakat qilasiz.
. Agar sessiyada arava mavjud bo'lmasa, bo'sh lug'atni o'rnatish orqali bo'sh savat yaratasiz
sessiya.
Siz kalit sifatida mahsulot identifikatorlari va har bir mahsulot kaliti uchun lug'at bilan savat lug'atini yaratasiz
miqdori va narxini o'z ichiga olgan qiymat bo'ladi. Buni amalga oshirish orqali siz mahsulotga kafolat bera olasiz
savatga bir martadan ortiq qo'shilmaydi. Shu tarzda siz savatdagi narsalarni olishni ham soddalashtirishingiz mumkin.
Keling, mahsulotlarni savatga qo'shish yoki ularning miqdorini yangilash usulini yarataylik. Quyidagi __add()__ ni qo'shing
va __Save()__ usullarini Cart sinfiga kiriting
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/b8f2f965-34f8-4c41-ba0f-4f115a263caf)
add() usuli quyidagi parametrlarni kiritish sifatida oladi:
* mahsulot: savatga qo‘shiladigan yoki yangilanadigan mahsulot namunasi.
* miqdor: mahsulot miqdori bilan ixtiyoriy butun son. Bu standart 1 ga teng.
* override_miqdori: Bu mantiqiy ko'rsatkich bo'lib, miqdorni berilgan miqdor (True) bilan oshib ketishi yoki yangi miqdorga qo'shilishi kerakligini ko'rsatadi.
mavjud miqdor (False)).

Siz mahsulot identifikatoridan savat tarkibi lug'atida kalit sifatida foydalanasiz. Siz mahsulot identifikatorini a ga aylantirasiz
string, chunki Django sessiya ma'lumotlarini ketma-ketlashtirish uchun JSON-dan foydalanadi va JSON faqat string kalit nomlariga ruxsat beradi.
Mahsulot identifikatori kalit va siz saqlaydigan qiymat miqdor va narx raqamlari bilan lug'atdir
mahsulot uchun. Mahsulotning narxi uni ketma-ketlashtirish uchun o'nlikdan satrga aylantiriladi. Nihoyat, siz
savatni sessiyada saqlash uchun save() usulini chaqiring.
save() usuli sessiyani session.modified = True yordamida o'zgartirilgan deb belgilaydi. Bu Djangoga aytadi
seans o'zgargan va uni saqlash kerak.
Shuningdek, mahsulotlarni savatdan olib tashlash usuli kerak. Savatga quyidagi usulni qo'shing
sinf:
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/e166567c-2fff-446d-b75f-5e361c7df13b)

Remove() usuli berilgan mahsulotni savat lug'atidan olib tashlaydi va save() usulini chaqiradi
seansda savatni yangilash uchun.
Siz savatdagi narsalarni takrorlashingiz va tegishli Mahsulotga pozitsiyalarda kirishingiz kerak bo'ladi. Buning uchun siz sinfingizda __iter__() usulini belgilashingiz mumkin. Quyidagi usulni qo'shing
Cart klassi:
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/b807a77c-f08d-48b7-9bfe-a7469f07e745)
__iter__() usulida siz savatda mavjud bo'lgan mahsulot namunalarini qo'shish uchun olasiz.
ularni savatdagi narsalar. Joriy savatni savat o‘zgaruvchisiga nusxalaysiz va Mahsulot namunalarini qo‘shasiz
bu. Nihoyat, siz savatdagi narsalarni takrorlaysiz, har bir mahsulot narxini o'nlik kassaga aylantirasiz va qo'shasiz.
har bir element uchun total_price atributi. Ushbu __iter__() usuli sizga osongina takrorlash imkonini beradi
ko'rinishlar va shablonlarda savatdagi narsalarni.
Shuningdek, savatdagi jami mahsulotlar sonini qaytarish usuli kerak. len() funksiyasi bajarilganda
ob'ektda Python uning uzunligini olish uchun __len__() usulini chaqiradi. Keyinchalik, siz a ni aniqlaysiz
savatda saqlangan narsalarning umumiy sonini qaytarish uchun maxsus __len__() usuli.
Cart sinfiga quyidagi __len__() usulini qo'shing
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/46454bd6-4650-447d-aa94-49a7d3bc6b4a)
Siz savatdagi barcha narsalar miqdorining yig'indisini qaytarasiz.
Savatdagi narsalarning umumiy narxini hisoblash uchun quyidagi usulni qo'shing
Nihoyat, savat seansini tozalash usulini qo'shing __clear__  ni.
![image](https://github.com/AsadbekNurmamatov2002/Django-darslar/assets/144318530/9b2346c4-1bf9-48e5-8829-fe55d8791c0c)




