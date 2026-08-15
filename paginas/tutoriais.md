---
titulo: "Tutoriais"
permalink: "/tutoriais"
layout: default
---

<div class="index-grid-item" markdown="1">
# Tutoriais

Visando facilitar o acesso à informações que MAPianos precisam buscar com alguma frequência, elaboramos alguns tutoriais.

Para sugestões ou envio de tutoriais, entre em contato pelo e-mail [labmap@usp.br](mailto:labmap@usp.br).

<div class="toc" markdown="1">
<ul>
{% for categoria in site.data.tutoriais_categorias %}
    <li>
        <a href="#{{ categoria.link }}">{{ categoria.nome }}</a>
        <ul>
        {% assign posts = site.posts | where: "categoria", categoria.nome | sort: "data" %}
        {% for post in posts %}
            <li><a href="#{{ post.link }}">{{ post.titulo }}</a></li>
        {% endfor %}
        </ul>
    </li>
{% endfor %}
</ul>
</div>

{% for categoria in site.data.tutoriais_categorias %}
## {{ categoria.nome }} {#{{categoria.link}}}

{% assign posts = site.posts | where: "categoria", categoria.nome | sort: "data" %}

<ul class="tutoriais-lista">
    {% for post in posts %}
        {% assign data = post.data | date: "%d/%m/%Y" %}
        {% include post.html %}
    {% endfor %}
</ul>
{% endfor %}

</div>