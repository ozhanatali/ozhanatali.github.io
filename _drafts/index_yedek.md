---
layout: default
title: Özhan Atalı
---

{% assign anasayfakategorileri = ''| split: '' %}
{% for ktgr in site.data.kategoriler %}
   {% assign anasayfakategorileri = ktgr.kategori | concat: anasayfakategorileri %}
{% endfor %}



<div id="home">

<! –– Giriş  ––> 
  
<div id="ana_linkler" style="text-align-last: center;"> 
<a href="/sozluk">Düşünce Sözlüğü</a> |
<a href="/sozluk">Başucu Linkleri</a> |
<a href="/sozluk">Site İçinde Ara</a> |   
</div>
   
<! –– tüm kategoriler  ––> 
   
 <h1>Konular:</h1>
   <ul class="posts">
   {% for cat in site.categories %}   
      <li><a href="https://ozhanatali.github.io/search?query={{ cat[0] }}" >{{ cat[0] }}</a>: {{ cat[1].size }} adet makale mevcut</li>
   {% endfor %}
   </ul>
   
<! –– tüm taglar  ––> 
   
  <h1>Altbaşlıklar:</h1>
    <ul class="posts">
   {% for tag in site.tags %}
      <a href="https://ozhanatali.github.io/search?query={{ tag[0] }}" >{{ tag[0] }}</a> [{{ tag[1].size }}]   
   {% endfor %}
   </ul>
   
   
  <h1>Son Yazılar</h1>
  <ul class="posts">
    {% for post in site.posts %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
     <li><a href="/sozluk">Devamı...</a></li>
  </ul>

<! –– data klasöründeki kategorilerin ana sayfada listelenmesi  ––> 

 {% for subcat in anasayfakategorileri %}
   {% for post in site.categories[subcat] %}
   {% if post[1].size>0 %} 
       {% assign ilgilikategori = site.data.kategoriler | where:"kategori", subcat | first %}
        <h1>{{ilgilikategori.baslik}}</h1>    
        {{ilgilikategori.aciklama}}
        <ul class="posts">
           {% for post in site.categories[subcat] %}
            <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
        </ul>
   {% endif %}
   {% endfor %}
 {% endfor %}


  
<! –– data klasöründeki linklerin ana sayfada listelenmesi  ––> 

<h1>Başucu Linkleri</h1>  
    <ul class="posts">
     {% for linkcik in site.data.linkler %}
      <li><a href={{ linkcik.link }} target="_blank" rel="noopener noreferrer"> {{ linkcik.baslik }} </a>: {{ linkcik.aciklama }} </li>
    {% endfor %}
  </ul>


   
</div>
